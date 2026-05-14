---
description: ARG academic-paper abstract-only mode — bilingual abstract + keywords
---

Trigger the `academic-paper` skill in `abstract-only` mode. Produces a bilingual (zh-TW + EN) abstract plus keywords. Fidelity spectrum, medium oversight. Carries the v3.6.7 `report_compiler_agent` PATTERN PROTECTION layer when invoked through the pipeline.

1. Read the skill entry at `academic-paper/SKILL.md` and locate the `abstract-only` mode section.
2. Read `MODE_REGISTRY.md` § academic-paper for mode triggers and output spec.
3. Read the report compiler agent at `agents/report_compiler_agent.md` for PATTERN PROTECTION rules.
4. Produce:
   - English abstract (150–250 words) with Background, Purpose, Method, Findings, Implications
   - Traditional Chinese (zh-TW) abstract
   - 5–7 keywords in both languages
5. Follow word count conventions from `shared/references/word_count_conventions.md`.
6. Include AI disclosure statement.
