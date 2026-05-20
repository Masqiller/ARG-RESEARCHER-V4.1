---
description: ARG deep-research full mode — APA 7.0 research report (3,000–8,000 words)
---

Trigger the `deep-research` skill in `full` mode. Runs a 13-agent pipeline for rigorous academic research on any topic. Produces a full APA 7.0 research report (3,000–8,000 words). Balanced-spectrum, high oversight.

1. Read the skill entry at `deep-research/SKILL.md` for the full 13-agent orchestration workflow.
2. Read `MODE_REGISTRY.md` § deep-research for mode details.
3. Execute the 6-stage research pipeline:
   - Stage 1 (Scoping): `rq_agent` formulates research question + methodology blueprint. Present to user for confirmation.
   - Stage 2 (Investigation): `search_agent` + `source_verifier_agent` — systematic literature search, source verification (Three-Layer citation protocol v3.7.3), risk of bias assessment.
   - Stage 3 (Analysis): `synthesis_agent` + `devils_advocate_agent` — cross-source synthesis, bias check, alternative explanations.
   - Stage 4 (Composition): `report_compiler_agent` — full APA 7.0 report with Writing Quality Check (remove AI-typical terms, sentence length variation).
   - Stage 5 (Review): `editorial_agent` + `ethics_agent` + `vulnerability_scanner_agent` — editorial review, ethics review, vulnerability scan.
   - Stage 6 (Revision): `revision_agent` — final polished report.
4. Apply Two-Layer citation protocol (v3.7.1) + Three-Layer citation protocol (v3.7.3) throughout.
5. Include AI disclosure statement in the final report.
6. If Style Profile is available from `academic-paper` intake, pass to `report_compiler_agent` as a soft guide.
