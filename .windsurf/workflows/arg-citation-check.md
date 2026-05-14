---
description: ARG academic-paper citation-check mode — citation error report
---

Trigger the `academic-paper` skill in `citation-check` mode. Produces a citation error report (missing references, mismatched in-text citations, format errors). Fidelity spectrum, low oversight.

1. Read the skill entry at `academic-paper/SKILL.md` and locate the `citation-check` mode section.
2. Read `MODE_REGISTRY.md` § academic-paper for mode triggers and output spec.
3. Analyze the provided paper for citation issues:
   - Missing references (cited in text but not in reference list)
   - Orphan references (in reference list but not cited in text)
   - Format inconsistencies (APA 7.0 compliance)
   - Mismatched author names, years, or page numbers
   - Incomplete citation entries
4. Produce a citation error report listing all issues found.
