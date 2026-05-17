# TikZ Pattern Library — Reusable Templates for `diagram_master_agent`

This library provides copy-paste-ready TikZ patterns for each supported diagram category. All patterns use the standard academic color palette and comply with the generation protocol in `diagram_generation_protocol.md`.

**Standard preamble** (add once per document):
```latex
\usepackage{tikz}
\usetikzlibrary{positioning, arrows.meta, shapes.geometric, calc, fit}
\definecolor{navy}{RGB}{0,31,63}
\definecolor{acadteal}{RGB}{0,128,128}
\definecolor{acadcrimson}{RGB}{153,0,0}
\definecolor{acadgold}{RGB}{180,130,0}
\definecolor{acadslate}{RGB}{90,100,110}
```

---

## Pattern 1 — Methodology / Process Flowchart (Categories 1 & 3)

For linear research flows, experimental protocols, and multi-step pipelines.

```latex
% Required: \usetikzlibrary{positioning, arrows.meta, shapes.geometric}
\begin{tikzpicture}[
  node distance=1.4cm,
  stage/.style={
    rectangle, draw=navy, fill=navy!8, rounded corners=3pt,
    minimum width=3.8cm, minimum height=0.9cm,
    font=\footnotesize\sffamily, text width=3.6cm, align=center
  },
  decision/.style={
    diamond, draw=acadteal, fill=acadteal!8, aspect=2.2,
    minimum height=1cm, font=\footnotesize\sffamily,
    inner sep=1pt, align=center
  },
  arrow/.style={-Stealth, thick, draw=navy!70},
  note/.style={font=\scriptsize\sffamily, text=acadslate, align=left}
]
  \node (s1) [stage] {Phase 1\\[2pt]\textit{[Step description]}};
  \node (s2) [stage, below=of s1] {Phase 2\\[2pt]\textit{[Step description]}};
  \node (dec) [decision, below=of s2] {[Decision?]};
  \node (s3a) [stage, below left=1.2cm and 1.8cm of dec] {Path A\\[2pt]\textit{[Action]}};
  \node (s3b) [stage, below right=1.2cm and 1.8cm of dec] {Path B\\[2pt]\textit{[Action]}};
  \node (s4) [stage, below=3.2cm of dec] {Phase 4\\[2pt]\textit{[Final step]}};

  \draw [arrow] (s1) -- (s2);
  \draw [arrow] (s2) -- (dec);
  \draw [arrow] (dec) -| node[note, above, pos=0.3] {Yes} (s3a);
  \draw [arrow] (dec) -| node[note, above, pos=0.3] {No}  (s3b);
  \draw [arrow] (s3a) |- (s4);
  \draw [arrow] (s3b) |- (s4);
\end{tikzpicture}
```

---

## Pattern 2 — Layered System Architecture (Category 2)

For system overviews, software layers, framework components.

```latex
% Required: \usetikzlibrary{positioning, arrows.meta, fit}
\begin{tikzpicture}[
  node distance=0.5cm,
  layer/.style={
    rectangle, draw=#1, fill=#1!6, rounded corners=2pt,
    minimum width=9cm, minimum height=1.3cm,
    font=\footnotesize\sffamily\bfseries, text=black
  },
  comp/.style={
    rectangle, draw=navy!50, fill=white,
    minimum width=2.4cm, minimum height=0.75cm,
    font=\scriptsize\sffamily, align=center, rounded corners=2pt
  },
  arrow/.style={-Stealth, draw=acadslate!70, thick}
]
  % Layer boxes (stacked vertically)
  \node (l3) [layer=navy] at (0, 0) {};
  \node [above=0.05cm of l3.west, anchor=west, font=\scriptsize\sffamily\bfseries, text=white] {Application Layer};
  \node (l2) [layer=acadteal, below=0.4cm of l3] {};
  \node [above=0.05cm of l2.west, anchor=west, font=\scriptsize\sffamily\bfseries, text=white] {Processing Layer};
  \node (l1) [layer=acadslate, below=0.4cm of l2] {};
  \node [above=0.05cm of l1.west, anchor=west, font=\scriptsize\sffamily\bfseries, text=white] {Data Layer};

  % Components inside layers
  \node (c1) [comp] at (l3.center) {[Component A]};
  \node (c2) [comp, right=0.4cm of c1] {[Component B]};
  \node (c3) [comp, left=0.4cm of c1] {[Component C]};
  \node (c4) [comp] at (l2.center) {[Module X]};
  \node (c5) [comp, right=0.4cm of c4] {[Module Y]};
  \node (c6) [comp] at (l1.center) {[Database]};
  \node (c7) [comp, right=0.4cm of c6] {[Storage]};

  % Inter-layer arrows
  \draw [arrow] (l3.south) -- (l2.north);
  \draw [arrow] (l2.south) -- (l1.north);
\end{tikzpicture}
```

---

## Pattern 3 — Theoretical Framework / Concept Map (Category 4)

For construct relationships, mediating variables, causal models.

```latex
% Required: \usetikzlibrary{positioning, arrows.meta}
\begin{tikzpicture}[
  node distance=2.5cm,
  construct/.style={
    rectangle, draw=navy, fill=navy!8, rounded corners=4pt,
    minimum width=3cm, minimum height=1cm,
    font=\footnotesize\sffamily, align=center
  },
  mediator/.style={
    ellipse, draw=acadteal, fill=acadteal!8,
    minimum width=2.8cm, minimum height=0.9cm,
    font=\footnotesize\sffamily, align=center
  },
  rel/.style={-Stealth, thick, draw=navy!70},
  mod/.style={-Stealth, dashed, draw=acadgold!80, thick},
  edge_label/.style={font=\scriptsize\sffamily, text=acadslate, fill=white, inner sep=1pt}
]
  \node (iv) [construct] {[Independent\\Variable]};
  \node (dv) [construct, right=5cm of iv] {[Dependent\\Variable]};
  \node (med) [mediator, right=2.5cm of iv] {[Mediator]};
  \node (mod) [construct, above=1.8cm of med] {[Moderator]};

  \draw [rel] (iv) -- node[edge_label, above] {(+)} (med);
  \draw [rel] (med) -- node[edge_label, above] {(+)} (dv);
  \draw [rel, bend right=20] (iv) to node[edge_label, below] {direct effect} (dv);
  \draw [mod] (mod) -- node[edge_label, right] {moderates} (med);
\end{tikzpicture}
```

---

## Pattern 4 — Commutative Diagram (Category 8)

For category theory, morphisms, functors.

```latex
% Required: \usepackage{tikz-cd}
\[\begin{tikzcd}[row sep=2.5em, col sep=3.5em,
    every arrow/.append style={-Stealth}]
  A \arrow[r, "f"] \arrow[d, "g"']
    & B \arrow[d, "h"] \\
  C \arrow[r, "k"']
    & D
  \arrow[from=1-1, to=2-2, "\phi", near start, crossing over]
\end{tikzcd}\]
```

For larger commutative diagrams:

```latex
\[\begin{tikzcd}[row sep=3em, col sep=4em]
  A \arrow[r, "f"] \arrow[rd, "\psi"'] \arrow[d, "g"']
    & B \arrow[d, "h"] \arrow[rd, "\alpha"] \\
  C \arrow[r, "k"'] \arrow[rd, "\beta"']
    & D \arrow[r, "\gamma"'] \arrow[d, "\delta"]
    & E \\
  & F \arrow[ru, "\epsilon"']
\end{tikzcd}\]
```

---

## Pattern 5 — Taxonomy / Hierarchy Tree (Category 6)

```latex
% Required: \usepackage{forest}
\begin{forest}
  for tree={
    draw=navy, fill=navy!5, rounded corners=2pt,
    edge={-Stealth, navy!60, thick},
    font=\footnotesize\sffamily,
    minimum height=0.75cm, minimum width=2.2cm,
    l sep=1.5cm, s sep=0.6cm,
    align=center, text width=2cm
  },
  where level=0{fill=navy!15, font=\footnotesize\sffamily\bfseries}{}
  [[Root Category]
    [[Sub-Cat A]
      [[Leaf A1]]
      [[Leaf A2]]
    ]
    [[Sub-Cat B]
      [[Leaf B1]]
    ]
    [[Sub-Cat C]
      [[Leaf C1]]
      [[Leaf C2]]
      [[Leaf C3]]
    ]
  ]
\end{forest}
```

---

## Pattern 6 — State Machine / Automata (Category 12)

```latex
% Required: \usetikzlibrary{automata, positioning, arrows.meta}
\begin{tikzpicture}[
  node distance=3.5cm,
  ->, >=Stealth, thick,
  every state/.style={
    draw=navy, fill=navy!8,
    font=\footnotesize\sffamily,
    minimum size=1.2cm
  },
  every edge/.append style={draw=navy!70, font=\scriptsize\sffamily}
]
  \node [state, initial] (s0) {Idle};
  \node [state, right=of s0] (s1) {Active};
  \node [state, right=of s1] (s2) {Processing};
  \node [state, accepting, below=2cm of s1] (s3) {Done};

  \path (s0) edge node[above] {start} (s1)
        (s1) edge node[above] {trigger} (s2)
        (s2) edge node[right] {complete} (s3)
        (s2) edge[bend left] node[below] {error} (s1)
        (s3) edge[bend right=40] node[left] {reset} (s0);
\end{tikzpicture}
```

---

## Pattern 7 — Timeline (Category 11)

```latex
% Required: \usetikzlibrary{positioning, arrows.meta}
\begin{tikzpicture}[
  event/.style={
    rectangle, draw=navy, fill=navy!8, rounded corners=2pt,
    minimum width=2.5cm, minimum height=0.8cm,
    font=\scriptsize\sffamily, align=center, text width=2.3cm
  },
  phase/.style={
    rectangle, draw=acadteal, fill=acadteal!6,
    minimum height=0.5cm, font=\scriptsize\sffamily,
    align=center
  },
  tick/.style={draw=navy!60, thick}
]
  % Main timeline axis
  \draw [-Stealth, very thick, draw=navy!80] (0,0) -- (12,0)
    node[right, font=\footnotesize\sffamily] {Time};

  % Tick marks and labels
  \foreach \x/\y in {1/2018, 3/2019, 5/2020, 7/2021, 9/2022, 11/2023} {
    \draw [tick] (\x, 0.15) -- (\x, -0.15);
    \node [below, font=\scriptsize\sffamily, text=navy] at (\x, -0.15) {\y};
  }

  % Events above the line
  \node [event, above=0.6cm] at (1, 0) {Phase 1\\Event A};
  \node [event, above=0.6cm] at (4, 0) {Phase 2\\Event B};
  \node [event, above=0.6cm] at (7, 0) {Phase 3\\Event C};
  \node [event, above=0.6cm] at (10, 0) {Phase 4\\Event D};

  % Connecting lines
  \foreach \x in {1, 4, 7, 10}
    \draw [tick, dashed] (\x, 0) -- (\x, 0.6);
\end{tikzpicture}
```

---

## Pattern 8 — Neural Architecture (Category 9, Hand-crafted TikZ)

For Transformer/attention diagrams when PlotNeuralNet is unavailable.

```latex
% Required: \usetikzlibrary{positioning, arrows.meta, fit}
\begin{tikzpicture}[
  node distance=0.7cm,
  tblock/.style={
    rectangle, draw=navy, fill=navy!10, rounded corners=2pt,
    minimum width=3cm, minimum height=0.75cm,
    font=\scriptsize\sffamily, align=center
  },
  attnblock/.style={
    rectangle, draw=acadteal, fill=acadteal!10, rounded corners=2pt,
    minimum width=3cm, minimum height=0.75cm,
    font=\scriptsize\sffamily, align=center
  },
  arrow/.style={-Stealth, draw=navy!70},
  group/.style={rectangle, draw=acadslate!50, dashed, rounded corners=3pt,
                inner sep=6pt, label={[font=\scriptsize\sffamily, text=acadslate]above:#1}}
]
  % Encoder stack
  \node (pe) [tblock] {Positional Encoding};
  \node (attn) [attnblock, above=of pe] {Multi-Head Attention};
  \node (addnorm1) [tblock, above=of attn] {Add \& Norm};
  \node (ffn) [tblock, above=of addnorm1] {Feed Forward};
  \node (addnorm2) [tblock, above=of ffn] {Add \& Norm};
  \node (out) [tblock, above=of addnorm2, fill=acadgold!15, draw=acadgold] {Output};

  \begin{scope}[on background layer]
    \node [group={Encoder $\times N$}, fit=(attn)(addnorm1)(ffn)(addnorm2)] {};
  \end{scope}

  \draw [arrow] (pe) -- (attn);
  \draw [arrow] (attn) -- (addnorm1);
  \draw [arrow] (addnorm1) -- (ffn);
  \draw [arrow] (ffn) -- (addnorm2);
  \draw [arrow] (addnorm2) -- (out);

  % Residual connections
  \draw [arrow, draw=acadcrimson!70, dashed]
    (pe.east) -- ++(1.2,0) |- (addnorm1.east);
  \draw [arrow, draw=acadcrimson!70, dashed]
    (addnorm1.east) -- ++(1,0) |- (addnorm2.east);
\end{tikzpicture}
```

---

## Pattern 9 — Sequence Diagram (Category 5, TikZ manual approach)

```latex
% Required: \usetikzlibrary{positioning, arrows.meta}
\begin{tikzpicture}[
  actor/.style={
    rectangle, draw=navy, fill=navy!8,
    minimum width=2.2cm, minimum height=0.8cm,
    font=\footnotesize\sffamily, align=center
  },
  lifeline/.style={draw=navy!40, dashed},
  msg/.style={-Stealth, draw=navy!70, font=\scriptsize\sffamily}
]
  % Actors
  \node (a1) [actor] at (0, 0) {Client};
  \node (a2) [actor] at (4, 0) {Server};
  \node (a3) [actor] at (8, 0) {Database};

  % Lifelines
  \draw [lifeline] (a1.south) -- ++(0,-6);
  \draw [lifeline] (a2.south) -- ++(0,-6);
  \draw [lifeline] (a3.south) -- ++(0,-6);

  % Messages (adjust y-coordinates for spacing)
  \draw [msg] (0,-1) -- node[above]{\small Request} (4,-1);
  \draw [msg] (4,-1.8) -- node[above]{\small Query} (8,-1.8);
  \draw [msg, dashed] (8,-2.6) -- node[above]{\small Result} (4,-2.6);
  \draw [msg, dashed] (4,-3.4) -- node[above]{\small Response} (0,-3.4);
\end{tikzpicture}
```

---

## Pattern 10 — Comparison Matrix (Category 7)

For feature comparison across multiple approaches/systems.

```latex
% Required: \usetikzlibrary{positioning, arrows.meta, matrix}
\begin{tikzpicture}[
  header/.style={font=\footnotesize\sffamily\bfseries, text=white, fill=navy, minimum height=0.8cm},
  row_label/.style={font=\footnotesize\sffamily, fill=navy!8, minimum width=2.5cm, minimum height=0.7cm, align=center},
  cell_yes/.style={font=\footnotesize\sffamily, fill=acadteal!20, minimum width=1.8cm, minimum height=0.7cm, align=center},
  cell_no/.style={font=\footnotesize\sffamily, fill=white, minimum width=1.8cm, minimum height=0.7cm, align=center, text=acadslate}
]
  \matrix [matrix of nodes, nodes in empty cells, row sep=-\pgflinewidth, column sep=-\pgflinewidth] {
    |[header, minimum width=2.5cm]| Feature &
    |[header, minimum width=1.8cm]| Method A &
    |[header, minimum width=1.8cm]| Method B &
    |[header, minimum width=1.8cm]| Method C \\
    |[row_label]| Property 1 & |[cell_yes]| \checkmark & |[cell_no]| -- & |[cell_yes]| \checkmark \\
    |[row_label]| Property 2 & |[cell_no]| -- & |[cell_yes]| \checkmark & |[cell_yes]| \checkmark \\
    |[row_label]| Property 3 & |[cell_yes]| \checkmark & |[cell_yes]| \checkmark & |[cell_no]| -- \\
  };
\end{tikzpicture}
```
