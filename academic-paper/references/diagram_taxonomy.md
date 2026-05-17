# Diagram Taxonomy — 13-Category Classification & Auto-Detection Logic

Used by `diagram_master_agent` (Dr. Atlas) Planner sub-role to identify diagram opportunities in a paper outline or draft.

---

## Category Table

| # | Category | Diagram Types | Primary Engine | Secondary Engine |
|---|----------|--------------|---------------|-----------------|
| 1 | **Methodology Flowchart** | Research design, data collection pipeline, sampling procedures, experimental protocol | TikZ (nodes + arrows) | Mermaid `flowchart` (draft only) |
| 2 | **System Architecture** | System overviews, framework layers, component diagrams, module relationships | TikZ (`fit`, `positioning`) | Mermaid `flowchart` (draft only) |
| 3 | **Process/Workflow** | Multi-stage pipelines, decision trees, algorithm flowcharts, data processing chains | TikZ (flowchart pattern) | Mermaid `flowchart` (draft only) |
| 4 | **Theoretical Framework** | Concept maps, variable relationship models, causal diagrams, construct maps | TikZ (`mindmap` or manual nodes) | — |
| 5 | **Sequence/Protocol** | Interaction sequences, protocol exchanges, API call chains, temporal ordering of events | TikZ (`pgf-umlsd` or manual) | Mermaid `sequenceDiagram` |
| 6 | **Hierarchy/Taxonomy** | Classification trees, organizational hierarchies, ontologies, category decompositions | TikZ (`forest` package) | — |
| 7 | **Comparison (Visual)** | Feature matrices (as diagrams not tables), paradigm comparisons with spatial layout, Venn-style overlaps | TikZ (matrix nodes) | — |
| 8 | **Mathematical/Commutative** | Commutative diagrams, morphisms, geometric constructions, proof trees | TikZ (`tikz-cd`) | N/A — TikZ only |
| 9 | **Neural/ML Architecture** | CNN, RNN, Transformer, U-Net, attention mechanisms, model pipeline diagrams | PlotNeuralNet / TikZ (3D blocks) | — |
| 10 | **Network/Graph** | Citation networks, collaboration graphs, dependency graphs, knowledge graphs | TikZ (`tikz-network` or raw) | — |
| 11 | **Timeline** | Historical progressions, literature evolution, project timelines, phase breakdowns | TikZ (manual timeline) | Mermaid `gantt` (draft only) |
| 12 | **State Machine** | Finite state machines, system state diagrams, protocol states, lifecycle diagrams | TikZ (`automata` library) | Mermaid `stateDiagram-v2` |
| 13 | **Mathematical Function Plots** | Parametric curves, function graphs, 3D surfaces, parametric plots without raw data | PGFPlots | — |

---

## Auto-Detection Heuristics

The Planner sub-role applies these triggers when scanning a paper outline or draft. Each trigger assigns a **candidate category** and an **initial necessity score** (refined after full-context assessment).

```
SCAN INPUT: Paper outline sections + chapter descriptions
─────────────────────────────────────────────────────────────────

├── TRIGGER 1 — Methodology section present?
│   └── YES → Candidate: Category 1 (Methodology Flowchart)
│             Initial score: 5/5 (essential for IMRaD papers)
│             Condition: IMRaD or empirical paper type
│
├── TRIGGER 2 — Multi-step process described in ≥3 sequential steps?
│   └── YES → Candidate: Category 3 (Process/Workflow)
│             Initial score: 4/5
│             Examples: "first... then... finally", numbered stages
│
├── TRIGGER 3 — Theoretical framework with ≥3 interconnected named constructs?
│   └── YES → Candidate: Category 4 (Theoretical Framework)
│             Initial score: 4/5
│             Examples: "X mediates the relationship between Y and Z"
│
├── TRIGGER 4 — System or architecture with ≥3 named components?
│   └── YES → Candidate: Category 2 (System Architecture)
│             Initial score: 5/5 (for CS/Engineering papers)
│             Initial score: 3/5 (for other disciplines)
│
├── TRIGGER 5 — Interactions between ≥2 named entities over time?
│   └── YES → Candidate: Category 5 (Sequence/Protocol)
│             Initial score: 3/5
│             Examples: client-server, agent-pipeline interactions
│
├── TRIGGER 6 — Classification or taxonomy with ≥2 levels described?
│   └── YES → Candidate: Category 6 (Hierarchy/Taxonomy)
│             Initial score: 4/5
│             Examples: "X can be classified into A, B, C; where A includes..."
│
├── TRIGGER 7 — Mathematical category theory, morphisms, or commuting diagrams?
│   └── YES → Candidate: Category 8 (Mathematical/Commutative)
│             Initial score: 5/5
│             Examples: functors, natural transformations, adjunctions
│
├── TRIGGER 8 — ML/DL model architecture described?
│   └── YES → Candidate: Category 9 (Neural/ML Architecture)
│             Initial score: 5/5 (for ML papers)
│             Examples: "encoder-decoder", "attention mechanism", "convolutional layers"
│
├── TRIGGER 9 — Comparison of ≥3 approaches with ≥2 dimensions?
│   └── YES (and no equivalent table exists) → Candidate: Category 7 (Comparison)
│             Initial score: 3/5
│             Suppress if comparison table already covers same information
│
├── TRIGGER 10 — Mathematical functions, parametric equations, or curves described?
│   └── YES → Candidate: Category 13 (Mathematical Function Plots)
│             Initial score: 4/5
│             Examples: "the loss function is described by...", "we plot f(x) = ..."
│
├── TRIGGER 11 — Network of relationships between nodes (non-hierarchical)?
│   └── YES → Candidate: Category 10 (Network/Graph)
│             Initial score: 3/5
│             Examples: citation network, co-author graph, concept dependency graph
│
├── TRIGGER 12 — Historical timeline or phase progression described?
│   └── YES → Candidate: Category 11 (Timeline)
│             Initial score: 3/5
│             Examples: "Phase 1 (2010–2015)... Phase 2 (2015–2020)..."
│
├── TRIGGER 13 — Finite state or lifecycle described?
│   └── YES → Candidate: Category 12 (State Machine)
│             Initial score: 3/5
│             Examples: "the system transitions from idle to active when..."
│
└── DEFAULT — Section prose > 600 words with no diagram trigger hit?
    └── ADVISORY: Suggest "Consider a visual aid for this section" (score: 2/5)
                  Do NOT auto-generate; present as suggestion only
```

---

## Necessity Score Scale

| Score | Label | Default Action |
|-------|-------|----------------|
| 5 | **Essential** | Generate automatically; include in draft without explicit user approval |
| 4 | **Strongly Recommended** | Generate; present to user for approval before embedding |
| 3 | **Recommended** | Add to Diagram Plan; generate on user request or explicit approval |
| 2 | **Optional** | Note in Diagram Plan as advisory; do not generate unless requested |
| 1 | **Decorative** | Suppress entirely; do not surface to user |

### Score Adjustment Rules

- **Paper type modifier**:
  - CS/Engineering/ML papers: +1 to Category 2, 9
  - Humanities/Policy papers: -1 to Category 2, 9; +1 to Category 4, 6
  - Medical/Clinical papers: +1 to Category 1, 5
  - Mathematics papers: +1 to Category 8, 13

- **Paper length modifier**:
  - Paper < 3,000 words: cap total diagrams at 2
  - Paper 3,000–6,000 words: cap at 4
  - Paper > 6,000 words: cap at floor(word_count / 1,500)

- **Suppression conditions** (force score to 0):
  - Section is Abstract or Conclusion
  - Equivalent comparison table already exists (Category 7)
  - Diagram would duplicate another planned diagram
  - Diagram ratio would exceed 1 per 1,000 words

---

## Category-Specific Guidance

### Category 1 — Methodology Flowchart

**Essential for**: IMRaD papers, empirical studies, mixed-methods studies, systematic reviews

**Typical structure**:
- Linear vertical flow (top-to-bottom)
- Decision diamonds at branching points (inclusion/exclusion, method selection)
- Parallel branches for concurrent procedures
- 4–8 stages is ideal; >10 stages → split into sub-figures

**TikZ packages**: `positioning`, `arrows.meta`, `shapes.geometric`

---

### Category 2 — System Architecture

**Essential for**: CS papers, software engineering, HCI, robotics, distributed systems

**Typical structure**:
- Layered horizontal or vertical groups (use `\begin{scope}` or `fit` nodes for layers)
- Components as boxes; communication as arrows with labels
- External systems as dashed-border boxes

**TikZ packages**: `positioning`, `fit`, `arrows.meta`

---

### Category 3 — Process/Workflow

**Use for**: Any multi-step procedure that benefits from visual sequencing

**Distinguish from Category 1**: Methodology diagrams describe research design; process diagrams describe a proposed system or procedure being studied.

**TikZ packages**: `positioning`, `arrows.meta`, `shapes.geometric`

---

### Category 4 — Theoretical Framework

**Essential for**: Theory-building papers, social science papers, literature review papers with conceptual synthesis

**Typical structure**:
- Central concept in the middle OR left-to-right causal flow
- Arrows labeled with relationship types (mediates, moderates, predicts)
- Variable boxes with construct names

**TikZ packages**: `positioning`, `arrows.meta`

---

### Category 5 — Sequence/Protocol

**TikZ approach**: Manual swimlane pattern with `\draw` lines; or `pgf-umlsd` package for UML-style sequence diagrams

**Mermaid acceptable**: `sequenceDiagram` when output is Markdown-only and diagram is ≤10 messages

---

### Category 6 — Hierarchy/Taxonomy

**Use `forest` package** for clean tree layouts. The `forest` package handles spacing and alignment automatically — never use manual TikZ node trees for hierarchical data.

**Required package**: `\usepackage{forest}`

---

### Category 7 — Comparison (Visual)

**Only generate if**: A table does NOT already present the same comparison. If a table exists, suppress this category.

**Suitable for**: Paradigm comparisons where spatial proximity/overlap encodes meaning (e.g., Venn overlaps, 2×2 positioning matrices)

---

### Category 8 — Mathematical/Commutative

**Always use `tikz-cd`** — it handles arrow spacing, label positioning, and cd-specific syntax correctly.

**Required package**: `\usepackage{tikz-cd}`

**Syntax reminder**: `\[\begin{tikzcd} ... \end{tikzcd}\]`

---

### Category 9 — Neural/ML Architecture

**PlotNeuralNet** for standard CNN/ResNet/U-Net layer stacks. For Transformers and attention: hand-craft TikZ using 3D-block patterns.

**Note PlotNeuralNet limitations explicitly** in the Diagram Code Block header if used.

---

### Category 10 — Network/Graph

**Use `tikz-network` package** if available; otherwise raw TikZ with `\node` + `\draw` edges.

**Cap at 30 nodes** for readability; larger graphs → sample a representative subgraph and note in caption.

---

### Category 11 — Timeline

**Standard pattern**: Horizontal line with tick marks and labels below; phase boxes above or below.

**Mermaid `gantt`** acceptable for draft/Markdown-only output when ≤8 phases.

---

### Category 12 — State Machine

**Use `automata` library** (`\usetikzlibrary{automata}`). State nodes use `state` style; transitions use `\path` with `edge` and `node` for labels.

**Mermaid `stateDiagram-v2`** acceptable for draft/Markdown-only output.

---

### Category 13 — Mathematical Function Plots

**Use PGFPlots**, not matplotlib. PGFPlots generates vector graphics natively in LaTeX.

**Required package**: `\usepackage{pgfplots}` + `\pgfplotsset{compat=1.18}`

**Use for**: Loss curves described analytically, parametric equations, 2D/3D function surfaces, mathematical illustrations of theoretical models.

**Do NOT use for**: Plotted experimental data (use `visualization_agent` / matplotlib for actual data).

**Required packages**:
```latex
\usepackage{pgfplots}
\pgfplotsset{compat=1.18}
```

**Basic pattern**:
```latex
\begin{tikzpicture}
  \begin{axis}[
    xlabel={$x$}, ylabel={$f(x)$},
    grid=major, grid style={dashed, gray!30},
    font=\footnotesize\sffamily
  ]
    \addplot[thick, navy, domain=-3:3, samples=100] {exp(-x^2)};
  \end{axis}
\end{tikzpicture}
```
