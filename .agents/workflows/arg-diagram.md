Trigger the `academic-paper` skill in `diagram` mode. Generates standalone structural/conceptual diagrams as compilable TikZ, PGFPlots, or Mermaid code.

1. Read `academic-paper/agents/diagram_master_agent.md` for Dr. Atlas's full capabilities and engine rules.
2. Read `academic-paper/references/diagram_taxonomy.md` for the 13 category definitions and auto-detection heuristics.
3. Read `academic-paper/references/diagram_generation_protocol.md` for generation rules per engine.
4. Ask clarifying questions:
   - What concept or process should the diagram show?
   - Which section of the paper will it appear in?
   - Output format: LaTeX (TikZ/PGFPlots) or Markdown (Mermaid)?
   - Color palette: default academic (navy/teal/crimson/gold/slate), monochrome, or custom?
5. Classify the request into one of 13 diagram categories and select the appropriate engine.
6. Generate complete, compilable code:
   - Include \caption{}, \label{}, and required preamble packages for LaTeX
   - Include an in-text reference: Figure~\ref{fig:label}
   - Follow all rules from `diagram_generation_protocol.md`
7. Run Validator self-check:
   - Syntax validity, package declarations present, \label matches \ref, caption present
8. Present output. Offer up to 2 refinement rounds based on user feedback.
