---
description: ARG academic-paper-reviewer calibration mode — FNR/FPR/AUC calibration report + session-scoped confidence disclosure
---

Trigger the `academic-paper-reviewer` skill in `calibration` mode (v3.2). Measures this reviewer's False Negative Rate / False Positive Rate / balanced accuracy against a user-supplied gold set of papers with known outcomes. Fidelity-spectrum, medium oversight. Opt-in — run once per domain before relying on rubric scores.

1. Read the skill entry at `academic-paper-reviewer/SKILL.md` and locate the `calibration` mode section.
2. Read `academic-paper-reviewer/references/calibration_mode_protocol.md` for full spec: intake rules, ensembling methodology, output format, and failure cases this mode does not fix.
3. Read `MODE_REGISTRY.md` § academic-paper-reviewer for mode details.
4. Intake: request 5–20 gold papers from the user, each with a known outcome (Accept / Reject / Revision + final decision after revision).
5. For each gold paper: run `full` mode 5× with fresh context (cross-model default-on); ensemble the 5 decisions.
6. Compute calibration metrics:
   - False Negative Rate (FNR): proportion of true Accepts misclassified as Reject/Major Revision.
   - False Positive Rate (FPR): proportion of true Rejects misclassified as Accept/Minor Revision.
   - Balanced accuracy: (1 − FNR + 1 − FPR) / 2.
   - Per-dimension calibration error (originality, methodology, domain, significance).
7. Produce Calibration Report:
   - FNR / FPR / balanced accuracy / AUC summary.
   - Per-dimension calibration error table.
   - Known failure cases (what this calibration does NOT fix).
8. Attach Calibration Report as a session-scoped confidence disclosure to all subsequent reviews in this session.
