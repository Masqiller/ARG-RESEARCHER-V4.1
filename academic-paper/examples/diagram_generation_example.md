# Diagram Generation Example — Full Pipeline Walk-Through

Demonstrates `diagram_master_agent` (Dr. Atlas) operating across Planner → Generator → Validator phases for a CS paper on transformer architectures.

**Paper**: "Efficient Code Generation Using Sparse Transformer Architectures"  
**Type**: Conference paper (CS / ML)  
**Output**: LaTeX (IEEE format)

---

## Phase 2D: Planner Output (After Outline)

After `structure_architect_agent` produces the outline, Dr. Atlas scans it:

**[Dr. Atlas — Planner Mode]**

> I've scanned your paper outline and identified the following diagram opportunities:

| ID | Diagram | Section | Category | Engine | Score |
|----|---------|---------|----------|--------|-------|
| D1 | Training Pipeline | §3 Methodology | 1 | TikZ | 5/5 |
| D2 | Sparse Transformer Architecture | §4 Model Design | 9 | TikZ | 5/5 |
| D3 | Attention Sparsity Pattern | §4.2 Mechanism | 7 | TikZ | 4/5 |
| D4 | Related Work Taxonomy | §2 Background | 6 | TikZ (forest) | 4/5 |
| D5 | Evaluation Protocol Flow | §5 Experiments | 3 | TikZ | 3/5 |
| D6 | Results Comparison Matrix | §6 Results | — | Skip | 1/5 |

> D6 (Results Comparison Matrix) is suppressed — a comparison table already covers this data.  
> D5 will be generated on request (score 3).  
> D1–D4 are ready for generation (scores 4–5). Shall I proceed?

**User**: Yes, go ahead with D1–D4.

---

## Phase 4: Generator Output

### Figure D1 — Training Pipeline (Category 1, TikZ)

```latex
% ============================================================
% Figure D1: Training Pipeline
% diagram_master_agent (Dr. Atlas) | Category 1 | Engine: TikZ
% Necessity: 5/5 | Placement: inline
%
% Required preamble additions:
%   \usepackage{tikz}
%   \usetikzlibrary{positioning, arrows.meta, shapes.geometric}
%   \definecolor{navy}{RGB}{0,31,63}
%   \definecolor{acadteal}{RGB}{0,128,128}
%   \definecolor{acadslate}{RGB}{90,100,110}
% ============================================================
\begin{figure}[htbp]
  \centering
  \begin{tikzpicture}[
    node distance=1.4cm,
    stage/.style={
      rectangle, draw=navy, fill=navy!8, rounded corners=3pt,
      minimum width=3.6cm, minimum height=0.9cm,
      font=\footnotesize\sffamily, text width=3.4cm, align=center
    },
    arrow/.style={-Stealth, thick, draw=navy!70},
    note/.style={font=\scriptsize\sffamily, text=acadslate}
  ]
    \node (corpus)  [stage] {Raw Code Corpus\\(GitHub, 54B tokens)};
    \node (tok)     [stage, below=of corpus] {BPE Tokenization\\(vocab: 50,000)};
    \node (pretrain)[stage, below=of tok] {Sparse Pre-training\\($N=12$, sparsity $k=64$)};
    \node (finetune)[stage, below=of pretrain] {Task Fine-tuning\\(HumanEval, MBPP)};
    \node (eval)    [stage, below=of finetune, fill=acadteal!10, draw=acadteal] {Evaluation\\(pass@1, pass@10)};

    \draw [arrow] (corpus)   -- (tok);
    \draw [arrow] (tok)      -- (pretrain);
    \draw [arrow] (pretrain) -- (finetune);
    \draw [arrow] (finetune) -- (eval);

    % Annotation
    \node [note, right=0.6cm of pretrain] {16$\times$ A100 GPUs\\72 hours};
  \end{tikzpicture}
  \caption{Training pipeline for the proposed sparse Transformer model.
           Tokenization uses byte-pair encoding with a 50,000-token vocabulary.
           Pre-training employs top-$k$ sparse attention ($k=64$).}
  \label{fig:training-pipeline}
\end{figure}
```

**In-text reference**: "As shown in Figure~\ref{fig:training-pipeline}, the training pipeline comprises five stages..."

---

### Figure D2 — Sparse Transformer Architecture (Category 9, TikZ)

```latex
% ============================================================
% Figure D2: Sparse Transformer Architecture
% diagram_master_agent (Dr. Atlas) | Category 9 | Engine: TikZ
% Necessity: 5/5 | Placement: full-page
%
% Required preamble additions:
%   \usetikzlibrary{positioning, arrows.meta, fit}
%   \usepackage{tikz}
% ============================================================
\begin{figure}[htbp]
  \centering
  \begin{tikzpicture}[
    node distance=0.65cm,
    tblock/.style={
      rectangle, draw=navy, fill=navy!10, rounded corners=2pt,
      minimum width=3.2cm, minimum height=0.75cm,
      font=\scriptsize\sffamily, align=center
    },
    sparseblock/.style={
      rectangle, draw=acadteal, fill=acadteal!10, rounded corners=2pt,
      minimum width=3.2cm, minimum height=0.75cm,
      font=\scriptsize\sffamily, align=center
    },
    arrow/.style={-Stealth, draw=navy!70, thick},
    res/.style={-Stealth, dashed, draw=acadcrimson!60},
    groupbox/.style={rectangle, draw=acadslate!50, dashed, rounded corners=4pt, inner sep=8pt}
  ]
    \node (embed)   [tblock] {Token + Pos. Embedding};
    \node (sattn)   [sparseblock, above=of embed] {Sparse Multi-Head Attn.\\($k$-nearest neighbors)};
    \node (norm1)   [tblock, above=of sattn] {Layer Norm + Residual};
    \node (ffn)     [tblock, above=of norm1] {Feed-Forward Network\\($d_{ff} = 4d_{model}$)};
    \node (norm2)   [tblock, above=of ffn] {Layer Norm + Residual};
    \node (output)  [tblock, above=of norm2, fill=acadgold!15, draw=acadgold] {Output Projection};

    % Stack grouping box
    \node [groupbox, fit=(sattn)(norm1)(ffn)(norm2),
           label={[font=\scriptsize\sffamily, text=acadslate]right:$\times 12$}] {};

    \draw [arrow] (embed)  -- (sattn);
    \draw [arrow] (sattn)  -- (norm1);
    \draw [arrow] (norm1)  -- (ffn);
    \draw [arrow] (ffn)    -- (norm2);
    \draw [arrow] (norm2)  -- (output);

    % Residual connections
    \draw [res] (embed.east)  -- ++(2,0) |- (norm1.east);
    \draw [res] (norm1.east)  -- ++(1.5,0) |- (norm2.east);
  \end{tikzpicture}
  \caption{Architecture of the proposed sparse Transformer encoder block.
           Sparse attention selects the top-$k$ most relevant tokens per query position.
           Dashed lines indicate residual connections.}
  \label{fig:sparse-transformer}
\end{figure}
```

**In-text reference**: "Figure~\ref{fig:sparse-transformer} illustrates the encoder block. Unlike dense attention..."

---

### Figure D4 — Related Work Taxonomy (Category 6, TikZ forest)

```latex
% ============================================================
% Figure D4: Related Work Taxonomy
% diagram_master_agent (Dr. Atlas) | Category 6 | Engine: TikZ (forest)
% Necessity: 4/5 | Placement: inline
%
% Required preamble additions:
%   \usepackage{forest}
%   \usetikzlibrary{arrows.meta}
% ============================================================
\begin{figure}[htbp]
  \centering
  \begin{forest}
    for tree={
      draw=navy, fill=navy!5, rounded corners=2pt,
      edge={-Stealth, navy!60, thick},
      font=\scriptsize\sffamily,
      minimum height=0.7cm, minimum width=2cm,
      l sep=1.4cm, s sep=0.5cm,
      align=center, text width=1.9cm
    },
    where level=0{fill=navy!15, font=\scriptsize\sffamily\bfseries, text=white}{}
    [Code Generation
      [Seq2Seq
        [RNN-based\\{[S1,S3]}]
        [LSTM-based\\{[S2,S4]}]
      ]
      [Transformer
        [Dense Attn.\\{[S5,S6]}]
        [Sparse Attn.\\{[S7,S8]}\\(ours)]
        [Retrieval-Aug.\\{[S9]}]
      ]
      [LLM-based
        [Codex\\{[S10]}]
        [CodeGen\\{[S11]}]
        [StarCoder\\{[S12]}]
      ]
    ]
  \end{forest}
  \caption{Taxonomy of neural code generation approaches.
           Square brackets indicate references in this survey.
           ``(ours)'' marks the proposed approach category.}
  \label{fig:taxonomy}
\end{figure}
```

**In-text reference**: "Figure~\ref{fig:taxonomy} presents a taxonomy of code generation approaches. We position our work in the sparse attention Transformer category..."

---

## Phase 5c: Validator Output — Diagram Audit Report

```markdown
## Diagram Audit Report
**Paper**: Efficient Code Generation Using Sparse Transformer Architectures
**Validated by**: diagram_master_agent (Dr. Atlas) — Validator mode
**Date**: [timestamp]

| ID | Title | Syntax | Packages | Labels | Cross-ref | Caption Cites | Status |
|----|-------|--------|----------|--------|-----------|---------------|--------|
| D1 | Training Pipeline | PASS | PASS | PASS | PASS | N/A | VALIDATED |
| D2 | Sparse Transformer Arch. | PASS | PASS | PASS | PASS | N/A | VALIDATED |
| D3 | Attention Sparsity Pattern | PASS | PASS | WARN | PASS | N/A | NEEDS_REVIEW |
| D4 | Related Work Taxonomy | PASS | PASS | PASS | PASS | N/A | VALIDATED |

### Issues

**D3 — Label Warning**:
- Node label "k-NN sparse pattern" does not match paper terminology "top-k sparse attention" (used in §4.2 paragraph 3)
- Recommended fix: Change node label to "Top-$k$ Sparse Attention Pattern"

### Caption Citations Flagged to `citation_compliance_agent`

None — no source attributions in any captions.

### Summary

3/4 diagrams VALIDATED. D3 requires one label update before finalization.
Preamble injection summary included in Figure D1–D4 header comments.
```

---

## Final Integration

After validation, `formatter_agent` receives:
1. All 4 diagram `.tex` snippets (embedded inline in draft)
2. Consolidated preamble injection block
3. Diagram Audit Report

For IEEE format, `formatter_agent` adds to the LaTeX preamble:

```latex
% ---- diagram_master_agent preamble additions ----
\usepackage{tikz}
\usetikzlibrary{positioning, arrows.meta, shapes.geometric, fit, calc}
\usepackage{forest}
\definecolor{navy}{RGB}{0,31,63}
\definecolor{acadteal}{RGB}{0,128,128}
\definecolor{acadcrimson}{RGB}{153,0,0}
\definecolor{acadgold}{RGB}{180,130,0}
\definecolor{acadslate}{RGB}{90,100,110}
% ---- end diagram_master_agent preamble additions ----
```
