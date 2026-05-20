---
description: ARG deep-research review mode — reviewer report on provided text or paper
---

Trigger the `deep-research` skill in `review` mode. Evaluates a provided paper, report, or piece of text against the deep-research evidence standards. Produces a structured reviewer report. Balanced-spectrum, high oversight.

1. Read the skill entry at `deep-research/SKILL.md` and locate the `review` mode section.
2. Read `MODE_REGISTRY.md` § deep-research for mode details.
3. Input: a paper, report, or text provided by the user (paste or file path).
4. Execute review against deep-research quality criteria:
   - Research question clarity and scope appropriateness.
   - Literature coverage completeness (missing key sources).
   - Methodology appropriateness for the question.
   - Evidence quality (hierarchy: meta-analyses > RCTs > cohort > case reports > expert opinion).
   - Citation accuracy and APA 7.0 compliance.
   - Synthesis quality (integration vs. mere summary).
   - Logical consistency and argumentation chain.
   - Claim-to-evidence ratio (overclaiming / underclaiming).
5. Produce Reviewer Report:
   - Strengths (specific, cited).
   - Issues by severity (Critical / Major / Moderate / Minor), each with location and suggested fix.
   - Evidence gap list (missing sources that should be cited).
   - Overall quality score per dimension.
6. Note: this is a research-quality review, not a peer-review simulation. For structured peer review, use `/academic-paper-reviewer`.
