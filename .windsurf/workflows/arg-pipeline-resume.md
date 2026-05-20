---
description: ARG academic-pipeline resume mode — resume a prior pipeline run from a Material Passport reset boundary
---

Trigger the `academic-pipeline` skill in `resume_from_passport` mode (v3.6.3 opt-in). Resumes a prior pipeline run from a recorded Material Passport reset boundary in a fresh session. Fidelity-spectrum, high oversight.

1. Read the skill entry at `academic-pipeline/SKILL.md` and locate the `resume_from_passport` mode section.
2. Read `academic-pipeline/references/passport_as_reset_boundary.md` for full resume contract, gate conditions, and pending-decision protocol.
3. Read `shared/handoff_schemas.md` Schema 9 (Material Passport) for the passport data structure.
4. Prerequisites — verify both gates before proceeding:
   - **Emit gate**: The original session must have run with `ARS_PASSPORT_RESET=1` set. Without this flag, no `kind: boundary` entries exist and there is nothing to resume from.
   - **Resume gate**: No flag required in the current session. Any session can invoke `resume_from_passport=<hash>`.
5. Intake from user: `resume_from_passport=<hash>` (required) + optional `stage=<n>` and `mode=<m>` CLI overrides.
6. Execute the resume protocol:
   - Locate the `kind: boundary` entry in the Material Passport matching `<hash>`.
   - Verify no later `kind: resume` entry has already consumed this boundary (each boundary can only be resumed once).
   - If `pending_decision` is set in the boundary entry: fire the decision prompt to the user first — **this prompt cannot be skipped**, even when `stage=` is supplied.
   - Determine next stage via routing priority: (a) `stage=<n>` CLI override → (b) matched option's `next_stage` → (c) `next` field in the boundary entry.
   - `mode=<m>` CLI override applies on top of stage routing if supplied.
7. Resume the pipeline from the determined stage, loading all materials recorded in the passport.
8. Follow all pipeline checkpoint rules from `academic-pipeline/SKILL.md` (MANDATORY checkpoints cannot be skipped).
9. Note: invoke this in a **fresh session** — resuming in the same session that emitted the boundary provides no token savings.
