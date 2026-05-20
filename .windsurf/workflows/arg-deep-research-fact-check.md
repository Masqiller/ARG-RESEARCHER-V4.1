---
description: ARG deep-research fact-check mode — claim-by-claim verification report
---

Trigger the `deep-research` skill in `fact-check` mode. Verifies a list of claims or a provided text claim-by-claim against primary sources and evidence hierarchy. Fidelity-spectrum, medium oversight.

1. Read the skill entry at `deep-research/SKILL.md` and locate the `fact-check` mode section.
2. Read `MODE_REGISTRY.md` § deep-research for mode details.
3. Input: a list of claims, a passage, or a document to fact-check.
4. For each claim:
   - Identify the claim type (empirical, definitional, causal, normative).
   - Search for primary sources that confirm, contradict, or qualify the claim.
   - Apply evidence hierarchy (meta-analyses > RCTs > cohort > case reports > expert opinion).
   - Verdict: Supported / Partially Supported / Unsupported / Misleading / Unverifiable.
   - Confidence level: High / Medium / Low.
   - Correction or qualifying context if Partially Supported, Unsupported, or Misleading.
5. Produce Fact-Check Report:
   - Claim-by-claim verification table (Claim | Verdict | Confidence | Evidence | Correction).
   - Summary of overall accuracy (% supported, % unsupported, % unverifiable).
   - Key sources used.
6. Note any claims that cannot be verified with available sources — mark as Unverifiable, not Unsupported.
7. Include AI disclosure statement.
