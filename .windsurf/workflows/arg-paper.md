---
description: ARG academic-paper full mode — write a complete paper draft (standalone, no pipeline)
---

Trigger the `academic-paper` skill in `full` mode. Produces a complete, publication-ready paper draft directly — without running the full 10-stage academic-pipeline. Use this when you already have research materials or want to write a paper standalone. Balanced-spectrum, high oversight.

1. Read the skill entry at `academic-paper/SKILL.md` for the full 12-agent orchestration workflow.
2. Read `MODE_REGISTRY.md` § academic-paper for mode details.
3. Run the configuration interview (intake):
   - Paper type (journal article, conference paper, thesis chapter, review, etc.).
   - Discipline and target venue/journal.
   - Citation format (APA / Chicago / MLA / IEEE / Vancouver).
   - Output format (LaTeX / DOCX via Pandoc / PDF / Markdown).
   - Word count target and language.
   - Optional: Style Calibration (provide 3+ past papers to calibrate writing voice). See `shared/style_calibration_protocol.md`.
4. Execute the 8-stage paper writing pipeline:
   - Phase 1 (Literature): `literature_strategist_agent` — systematic search strategy, source screening, bibliography.
   - Phase 2 (Structure): `structure_architect_agent` — paper architecture, outline, word count allocation.
     - Parallel Phase 2D: `diagram_master_agent` Planner mode — scan outline for diagram opportunities, produce Diagram Plan.
   - Phase 3 (Argumentation): `argument_builder_agent` — claim-evidence chains (CER), logical flow blueprint.
   - Phase 4 (Drafting): `draft_writer_agent` — section-by-section full draft with figures/diagrams embedded.
   - Phase 5a (Citations): `citation_compliance_agent` — 100% citation format compliance, missing DOIs, self-citation ratio.
   - Phase 5b (Abstract): `abstract_agent` — bilingual abstract (zh-TW + EN) + keywords.
   - Phase 5c (Diagrams): `diagram_master_agent` Validator mode — syntax, package, label, caption-citation checks.
   - Phase 6 (Self-Review): `self_review_agent` — Writing Quality Check (AI-typical terms, sentence rhythm, paragraph variation).
   - Phase 7 (Revision): `revision_integrator_agent` — incorporate self-review feedback, finalize draft.
   - Phase 8 (Format): `format_converter_agent` — convert to chosen output format.
5. Apply Two-Layer citation protocol (v3.7.1) + Three-Layer citation protocol (v3.7.3) throughout.
6. Include AI disclosure statement in final output.
7. Note: this is standalone paper writing only. For the full research → write → review → revise pipeline, use `/arg-full`.
