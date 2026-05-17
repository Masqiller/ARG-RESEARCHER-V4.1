# Diagram Generation Protocol — TikZ, Mermaid, PGFPlots, PlotNeuralNet

Used by `diagram_master_agent` (Dr. Atlas) Generator sub-role.

> **Engine hierarchy**: TikZ (primary, all categories) → PGFPlots (Category 13) → PlotNeuralNet (Category 9 CNN/ResNet) → Mermaid (secondary, flowcharts/sequences in Markdown-only output)

---

## 1. General Generation Rules (All Engines)

1. **Every diagram must have a Diagram Plan entry** — Generator never creates a diagram not listed in the confirmed Diagram Plan (Schema 13), except in standalone `/arg-diagram` mode
2. **Preamble additions are mandatory** — list all required `\usepackage` and `\usetikzlibrary` lines in the Diagram Code Block header comment
3. **In-text reference is mandatory** — every generated diagram must be accompanied by an in-text reference string: `"As shown in Figure D[N], ..."`
4. **Caption is mandatory** — every `\begin{figure}` must contain a `\caption{}` and a `\label{fig:...}` with a semantic label
5. **Never silently fail** — if generation is not possible (e.g., package unavailable, diagram too complex), report the issue and suggest a fallback

---

## 2. TikZ Protocol (Primary Engine)

### 2.1 Required Structure

Every TikZ diagram must follow this structure:

```latex
% ============================================================
% Figure D[N]: [Title]
% diagram_master_agent (Dr. Atlas) | Category [1-13] | Engine: TikZ
% Necessity: [X]/5 | Placement: [inline/full-page/appendix]
%
% Required preamble additions:
%   \usepackage{tikz}
%   \usetikzlibrary{[libraries]}
%   % Color definitions (add once per document):
%   \definecolor{navy}{RGB}{0,31,63}
%   \definecolor{acadteal}{RGB}{0,128,128}
%   \definecolor{acadcrimson}{RGB}{153,0,0}
%   \definecolor{acadgold}{RGB}{180,130,0}
%   \definecolor{acadslate}{RGB}{90,100,110}
% ============================================================
\begin{figure}[htbp]
  \centering
  \begin{tikzpicture}[
    node distance=1.5cm,
    % Style definitions go here
  ]
    % Node definitions
    % Edge definitions
  \end{tikzpicture}
  \caption{[Caption text following APA 7.0 format.]}
  \label{fig:[semantic-label]}
\end{figure}
```

### 2.2 Style Definitions

Define ALL node styles at the top of the `tikzpicture` environment via `\tikzset{}` or inline options. Never place style definitions mid-diagram.

**Standard academic style set**:

```latex
\tikzset{
  box/.style={
    rectangle, draw=navy, fill=navy!8, rounded corners=3pt,
    minimum width=3.2cm, minimum height=0.9cm,
    font=\footnotesize\sffamily, text width=3cm, align=center
  },
  decision/.style={
    diamond, draw=acadteal, fill=acadteal!8,
    minimum width=2.2cm, minimum height=1.1cm,
    font=\footnotesize\sffamily, inner sep=2pt, align=center
  },
  arrow/.style={-Stealth, thick, draw=navy!70},
  dashed_arrow/.style={-Stealth, dashed, draw=acadslate!60},
  label_node/.style={font=\scriptsize\sffamily, text=acadslate}
}
```

### 2.3 Positioning Rules

- Use **relative positioning** exclusively: `right=2cm of nodeA`, `below=1.5cm of nodeB`
- Set `node distance` in the `tikzpicture` options for default spacing
- Use `calc` library for midpoint calculations: `($( A)!0.5!(B)$)`
- Use `fit` library to create bounding boxes around groups of nodes

### 2.4 Node Naming

- Use **semantic names**: `\node (methodology_phase) {Methodology}` — never `\node (n1) {}`
- Use snake_case for multi-word node names
- Camelcase is acceptable for established technical terms: `\node (multiHeadAttention) {}`

### 2.5 Complexity Limits

| Limit | Value | Action if exceeded |
|-------|-------|--------------------|
| Nodes per diagram | 80 | Split into sub-figures A/B |
| Nesting levels | 4 | Flatten or split |
| Distinct colors | 5 | Remove least-important color variation |
| Arrow label length | 4 words | Abbreviate or move to caption Note |

### 2.6 Multi-Panel Figures

When a diagram must be split:

```latex
\begin{figure}[htbp]
  \centering
  \begin{subfigure}[b]{0.48\textwidth}
    \centering
    \begin{tikzpicture}[...]
      % Panel A content
    \end{tikzpicture}
    \caption{[Panel A caption]}
    \label{fig:[label]-a}
  \end{subfigure}
  \hfill
  \begin{subfigure}[b]{0.48\textwidth}
    \centering
    \begin{tikzpicture}[...]
      % Panel B content
    \end{tikzpicture}
    \caption{[Panel B caption]}
    \label{fig:[label]-b}
  \end{subfigure}
  \caption{[Overall caption for the multi-panel figure.]}
  \label{fig:[label]}
\end{figure}
```

Required package: `\usepackage{subcaption}`

---

## 3. PGFPlots Protocol (Category 13 — Mathematical Function Plots)

**Use when**: The diagram represents a mathematical function, parametric curve, or analytical model — NOT experimental data (those go to `visualization_agent`).

### 3.1 Required Preamble

```latex
\usepackage{pgfplots}
\pgfplotsset{compat=1.18}
```

### 3.2 Standard Axis Style

```latex
\begin{tikzpicture}
  \begin{axis}[
    width=0.85\columnwidth,
    height=6cm,
    xlabel={$x$},
    ylabel={$f(x)$},
    xlabel style={font=\footnotesize\sffamily},
    ylabel style={font=\footnotesize\sffamily},
    tick label style={font=\scriptsize\sffamily},
    grid=major,
    grid style={dashed, gray!30},
    axis lines=left,
    legend style={font=\scriptsize\sffamily, at={(0.98,0.95)}, anchor=north east}
  ]
    \addplot[thick, color=navy, domain=-3:3, samples=150] {exp(-x^2)};
    \addlegendentry{Gaussian kernel}
  \end{axis}
\end{tikzpicture}
```

### 3.3 3D Surface Plot

```latex
\begin{tikzpicture}
  \begin{axis}[
    view={60}{30},
    xlabel={$x$}, ylabel={$y$}, zlabel={$f(x,y)$},
    colormap/viridis,
    font=\scriptsize\sffamily
  ]
    \addplot3[surf, domain=-2:2, domain y=-2:2, samples=30]
      {exp(-(x^2+y^2))};
  \end{axis}
\end{tikzpicture}
```

---

## 4. PlotNeuralNet Protocol (Category 9 — CNN/ResNet/U-Net only)

**Use when**: Paper contains a convolutional neural network, ResNet, U-Net, or similar layer-stack architecture.

### 4.1 Workflow

```
1. Clone: git clone https://github.com/HarisIqbal88/PlotNeuralNet
2. Create model definition file: mymodel.py
3. Run: python3 mymodel.py  (generates mymodel.tex)
4. Compile: pdflatex mymodel.tex  (generates mymodel.pdf)
5. Include: \includegraphics[width=\columnwidth]{figures/mymodel.pdf}
```

### 4.2 Layer Definition Syntax

```python
import sys
sys.path.append('../')
from pycore.tikzeng import *

arch = [
    to_head('..'),
    to_cor(),
    to_begin(),
    to_Conv("conv1", 64, 64, offset="(0,0,0)", to="(0,0,0)", height=40, depth=40, width=2),
    to_Pool("pool1", offset="(0,0,0)", to="(conv1-east)"),
    to_Conv("conv2", 32, 32, offset="(1,0,0)", to="(pool1-east)", height=32, depth=32, width=3),
    to_end()
]

def main():
    namefile = str(sys.argv[0]).split('.')[0]
    to_generate(arch, namefile + '.tex')

if __name__ == '__main__':
    main()
```

### 4.3 Fallback for Unsupported Architectures

For Transformers, RNNs, attention mechanisms (not supported by PlotNeuralNet), use hand-crafted TikZ with 3D-block visual style:

```latex
% Transformer block style
\tikzset{
  tblock/.style={
    rectangle, draw=navy, fill=navy!10, rounded corners=2pt,
    minimum width=2.5cm, minimum height=0.8cm,
    font=\scriptsize\sffamily, align=center
  },
  attn/.style={
    rectangle, draw=acadteal, fill=acadteal!10, rounded corners=2pt,
    minimum width=2.5cm, minimum height=0.8cm,
    font=\scriptsize\sffamily, align=center
  }
}
```

---

## 5. Mermaid Protocol (Secondary Engine — Restricted Use)

### 5.1 Permitted Use Cases ONLY

- (a) Output format is **Markdown only** (not LaTeX) AND the user has confirmed no LaTeX is needed
- (b) User explicitly requests a **quick draft or preview** before LaTeX finalization
- (c) Diagram type is **sequence** or **state machine** where TikZ adds no geometric value

**Always note** when using Mermaid instead of TikZ: add `<!-- Mermaid draft — generate TikZ version for final LaTeX -->` above the code block.

### 5.2 Required Header

Every Mermaid diagram must start with a title:

````markdown
```mermaid
---
title: [Descriptive Title]
---
[diagram type]
    [content]
```
````

### 5.3 Node Label Rules

- Maximum 5 words per node label
- No special characters in node IDs (`A[My Node]` not `A[My-Node!]`)
- Use `subgraph` for logical grouping (flowchart type only)

### 5.4 Arrow Type Conventions

| Relationship Type | Arrow | Mermaid Syntax |
|------------------|-------|----------------|
| Strong / direct | Solid | `-->` |
| Weak / optional | Dashed | `-.->` |
| Bidirectional | Double | `<-->` |
| Labeled | Solid + label | `-- label -->` |

### 5.5 Complexity Limit

Maximum 30 nodes per Mermaid diagram. If more nodes are needed, use TikZ instead.

---

## 6. Error Handling

| Error | Primary Action | Fallback |
|-------|---------------|---------|
| TikZ: missing semicolons | Auto-repair: add `;` after each `\node` and `\draw` statement | Regenerate |
| TikZ: unescaped underscores in text | Auto-repair: replace `_` with `\_` in node labels | Regenerate |
| TikZ: unbalanced braces | Auto-repair: scan and balance | Regenerate with simpler structure |
| TikZ: non-existent package requested | Replace with valid CTAN alternative; note limitation | Use basic `tikz` only |
| PGFPlots: version incompatibility | Add `\pgfplotsset{compat=1.18}` | Downgrade syntax to `compat=1.16` |
| PlotNeuralNet: unavailable | Use hand-crafted TikZ 3D-block style | Provide PlotNeuralNet setup instructions separately |
| Mermaid: circular dependency | Flag to user; restructure diagram or break cycle | Replace with TikZ |
| Any: diagram too complex | Split into sub-figures (label A, B, C) | Reduce scope to core elements only |

---

## 7. Output Verification Before Handoff

Before handing off to `draft_writer_agent` or `formatter_agent`, Generator must confirm:

- [ ] All `\begin{}` have matching `\end{}`
- [ ] All braces `{}` are balanced
- [ ] All node names referenced in edges exist
- [ ] `\caption{}` and `\label{fig:...}` are present
- [ ] Preamble additions are listed in the header comment
- [ ] In-text reference string is included with output
- [ ] No more than 5 distinct colors used
- [ ] No hardcoded absolute coordinates as sole positioning method
