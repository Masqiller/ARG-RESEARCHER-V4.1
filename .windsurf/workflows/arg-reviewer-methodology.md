---
description: ARG academic-paper-reviewer methodology-focus mode — in-depth methodology review
---

Trigger the `academic-paper-reviewer` skill in `methodology-focus` mode. Runs a 2-reviewer panel (EIC + methodology reviewer) with deep focus on research design, statistical validity, and reproducibility. Fidelity-spectrum, medium oversight. Sprint Contract v3.6.2 applies (2-reviewer panel).

1. Read the skill entry at `academic-paper-reviewer/SKILL.md` and locate the `methodology-focus` mode section.
2. Read `MODE_REGISTRY.md` § academic-paper-reviewer for mode details.
3. Read `academic-paper-reviewer/references/statistical_reporting_standards.md` for statistical red flags and APA 7.0 reporting standards.
4. Run `field_analyst_agent` to identify methodology type and research paradigm.
5. Run `eic_agent` (brief framing pass — journal fit + overall scope only).
6. Run `methodology_reviewer_agent` (deep pass):
   - Research design rigor and appropriateness.
   - Sampling strategy, sample size justification, statistical power.
   - Data collection and measurement validity.
   - Analysis method selection and statistical validity.
   - Effect sizes, confidence intervals, significance thresholds.
   - Reproducibility and data transparency.
   - Red flags from `references/statistical_reporting_standards.md`.
7. Produce In-depth Methodology Review Report with:
   - Scored rubric across all methodology dimensions (0–10 each).
   - Ordered list of issues (Critical → Major → Moderate → Minor).
   - Specific improvement suggestions for each issue (what, where, how to fix).
