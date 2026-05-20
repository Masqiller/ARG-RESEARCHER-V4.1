---
description: ARG academic-paper-reviewer quick mode — EIC quick assessment + key issues list (15-minute review)
---

Trigger the `academic-paper-reviewer` skill in `quick` mode. Produces an EIC quick assessment and key issues list in approximately 15 minutes. Fidelity-spectrum, low oversight.

1. Read the skill entry at `academic-paper-reviewer/SKILL.md` and locate the `quick` mode section.
2. Read `MODE_REGISTRY.md` § academic-paper-reviewer for mode details.
3. Run `field_analyst_agent` to identify discipline and venue tier (brief pass only).
4. Run `eic_agent` for a rapid top-level assessment:
   - Journal/venue fit (1–2 sentences).
   - Key strength (1 item).
   - Top 3 issues blocking acceptance (with severity: Critical / Major / Minor).
   - Preliminary recommendation (Accept / Minor Revision / Major Revision / Reject).
5. Output: EIC Quick Assessment Report (≤ 500 words) + Key Issues List (≤ 5 items).
6. No Devil's Advocate pass in quick mode; Iron Rule #4 does not apply.
7. Note to user: quick mode is a rapid filter, not a comprehensive review. Use `full` mode for pre-submission assessment.
