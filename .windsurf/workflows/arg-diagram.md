---
description: ARG academic-paper diagram mode — standalone structural & conceptual diagram generation (TikZ / Mermaid / PGFPlots / PlotNeuralNet)
---

Trigger the `academic-paper` skill in `diagram` mode via `diagram_master_agent` (Dr. Atlas). Generates publication-quality diagram code on demand, outside the full pipeline.

1. Read `academic-paper/agents/diagram_master_agent.md` to load Dr. Atlas's capabilities, engine rules, and anti-patterns.
2. Read `academic-paper/references/diagram_taxonomy.md` to understand the 13-category classification system.
3. Read `academic-paper/references/diagram_generation_protocol.md` for engine-specific generation rules (TikZ, PGFPlots, PlotNeuralNet, Mermaid).
4. Ask the user 2–3 clarifying questions about the diagram:
   - What does the diagram need to show? (components, relationships, flow direction)
   - What is the target output format? (LaTeX → default TikZ; Markdown → Mermaid acceptable)
   - Any specific elements, labels, or style preferences?
5. Classify the request against the 13-category taxonomy; select the appropriate engine.
6. Select the relevant pattern from `academic-paper/references/diagram_tikz_patterns.md` (TikZ) or `academic-paper/references/diagram_mermaid_patterns.md` (Mermaid).
7. Generate the complete diagram code:
   - Include full preamble additions required (`\usepackage`, `\usetikzlibrary`)
   - Wrap in `\begin{figure}...\end{figure}` with `\caption{}` and `\label{fig:...}` (LaTeX)
   - Add in-text reference string: "As shown in Figure X, ..."
   - Add the Mermaid draft comment if engine is Mermaid: `<!-- Mermaid draft — generate TikZ for final LaTeX -->`
8. Run the Validator self-check before presenting output:
   - Syntax: balanced braces, valid commands, no dangling edges
   - Packages: all `\usepackage` / `\usetikzlibrary` reference real CTAN packages
   - Anti-patterns: no decorative diagrams, no hardcoded absolute coordinates only
9. Present the complete Diagram Code Block to the user with integration instructions.
10. Offer up to 3 refinement rounds based on user feedback.
11. Follow all anti-patterns from `diagram_master_agent.md` Section "Anti-Patterns".
