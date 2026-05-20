---
description: ARG academic-paper-reviewer full mode — 5 reviewers + Editorial Decision + Revision Roadmap
---

Trigger the `academic-paper-reviewer` skill in `full` mode. Simulates 5 independent reviewers (EIC + 3 peer reviewers + Devil's Advocate) with field-specific expertise. Produces 5 review reports, an Editorial Decision Letter, and a Revision Roadmap. Balanced-spectrum, high oversight.

1. Read the skill entry at `academic-paper-reviewer/SKILL.md` for the full orchestration workflow.
2. Read `MODE_REGISTRY.md` § academic-paper-reviewer for mode details and sprint contract rules.
3. Execute Phase 0 — Field Analysis & Persona Configuration:
   - Run `field_analyst_agent` to identify primary/secondary discipline, methodology type, target venue tier, paper maturity.
   - Dynamically generate 5 reviewer identities (EIC, Methodology, Domain, Perspective, Devil's Advocate).
   - Present Reviewer Configuration Card to user for confirmation.
4. Execute Phase 1 — Parallel Independent Reviews (all 5 reviewers independently, no cross-referencing):
   - `eic_agent`: Journal fit, originality, overall significance.
   - `methodology_reviewer_agent`: Research design, statistical validity, reproducibility.
   - `domain_reviewer_agent`: Literature coverage, theoretical framework, domain contribution.
   - `perspective_reviewer_agent`: Cross-disciplinary connections, practical impact, ethical implications.
   - `devils_advocate_reviewer_agent`: Core argument challenges, logical fallacy detection, strongest counter-arguments, "So What?" test.
5. Execute Phase 2 — Editorial Synthesis & Decision:
   - `editorial_synthesizer_agent` consolidates all 5 reports.
   - Builds cross-reviewer consensus matrix (5-agree / split).
   - Applies Iron Rule #4: if Devil's Advocate finds CRITICAL issues → Decision cannot be Accept.
   - Produces Editorial Decision Letter + prioritised Revision Roadmap.
6. Trigger Phase 2.5 — Revision Coaching (Socratic) if Decision = Major/Minor Revision (skip with "just fix it").
7. Follow READ-ONLY constraint: never modify the submitted manuscript; produce reports only.
