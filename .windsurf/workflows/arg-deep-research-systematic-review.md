---
description: ARG deep-research systematic-review mode — PRISMA 2020 report (5,000–15,000 words) with optional meta-analysis
---

Trigger the `deep-research` skill in `systematic-review` mode. Produces a full PRISMA 2020 systematic review report (5,000–15,000 words) with optional meta-analysis. Fidelity-spectrum, medium oversight.

1. Read the skill entry at `deep-research/SKILL.md` and locate the `systematic-review` mode section.
2. Read `MODE_REGISTRY.md` § deep-research for mode details.
3. Input: PICO/PICOS question or research question from the user.
4. Execute PRISMA 2020 protocol:
   - Stage 1 (Protocol): Define PICO(S) — Population, Intervention, Comparator, Outcome, Study design. Specify inclusion/exclusion criteria. Confirm with user.
   - Stage 2 (Identification): Systematic search across multiple databases; record total hits per database.
   - Stage 3 (Screening): Title/abstract screening → full-text screening. Report exclusions with reasons (PRISMA flow diagram in text form).
   - Stage 4 (Inclusion): Final included studies list with extraction table (Study | Design | N | Intervention | Outcome | Risk of Bias).
   - Stage 5 (Risk of Bias): Assess each study using appropriate tool (RoB 2 for RCTs, ROBINS-I for observational, AMSTAR 2 for reviews).
   - Stage 6 (Synthesis): Narrative synthesis; if ≥3 homogeneous studies: offer meta-analysis (effect size, heterogeneity I², forest plot description).
   - Stage 7 (Report): Full PRISMA 2020 structured report.
5. Apply Three-Layer citation verification (v3.7.3) throughout.
6. Produce PRISMA 2020 Report with all required sections: Background, Methods, Results (PRISMA flow + study characteristics + synthesis), Discussion (limitations, certainty of evidence), Conclusions, References.
7. Include AI disclosure statement.
