---
description: ARG academic-paper-reviewer re-review mode — revision verification checklist + residual issues + new Decision
---

Trigger the `academic-paper-reviewer` skill in `re-review` mode. Verifies whether revisions address first-round review comments. Uses R&R Traceability Matrix (Schema 11). Fidelity-spectrum, medium oversight.

1. Read the skill entry at `academic-paper-reviewer/SKILL.md` and locate the `re-review` mode section.
2. Read `academic-paper-reviewer/references/re_review_mode_protocol.md` for full verification logic and output format.
3. Read `MODE_REGISTRY.md` § academic-paper-reviewer for mode details.
4. Inputs required: original Revision Roadmap + revised manuscript (+ optional Author Response to Reviewers).
5. For each item in the Revision Roadmap:
   - Locate the corresponding change in the revised manuscript.
   - Verify: Author's Claim → Evidence in manuscript → Verified? (Yes / Partial / No).
   - Flag any new issues introduced by the revision.
6. Produce Verification Review Report with:
   - R&R Traceability Matrix (Roadmap item | Author's Claim | Verified? | Notes).
   - List of residual issues (unaddressed from first round).
   - List of new issues introduced in revision.
   - New Editorial Decision (Accept / Minor Revision / Major Revision / Reject).
7. Anti-pattern: rubber-stamp re-review is forbidden — each concern must be independently verified against the revised text.
