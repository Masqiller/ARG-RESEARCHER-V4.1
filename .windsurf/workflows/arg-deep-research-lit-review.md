---
description: ARG deep-research lit-review mode — annotated bibliography + thematic synthesis
---

Trigger the `deep-research` skill in `lit-review` mode. Produces a structured annotated bibliography with thematic synthesis on a research topic. Fidelity-spectrum, medium oversight.

1. Read the skill entry at `deep-research/SKILL.md` and locate the `lit-review` mode section.
2. Read `MODE_REGISTRY.md` § deep-research for mode details.
3. Input: research topic or question from the user.
4. Execute literature review pipeline:
   - Stage 1: Scope the literature domain (key themes, time range, inclusion/exclusion criteria). Confirm with user.
   - Stage 2: Systematic search — identify 15–30 highly relevant sources across: seminal works, recent advances (last 5 years), methodological papers, review articles.
   - Stage 3: Apply Three-Layer citation verification (v3.7.3) to all sources.
   - Stage 4: Annotate each source: full citation (APA 7.0) + 3–5 sentence annotation (main argument, methodology, contribution to the field, limitations).
   - Stage 5: Thematic synthesis — group sources into 3–6 themes; write a synthesis paragraph for each theme.
5. Produce Annotated Bibliography output:
   - Introduction (scope statement, search strategy summary).
   - Thematic sections with synthesis paragraph + annotated entries.
   - Research gap identification.
   - Full reference list (APA 7.0).
6. Include AI disclosure statement.
