---
description: ARG academic-paper revision mode — revised draft + R&R responses
---

Trigger the `academic-paper` skill in `revision` mode. Produces a revised draft plus point-by-point response-to-reviewers. Fidelity spectrum, high oversight.

1. Read the skill entry at `academic-paper/SKILL.md` and locate the `revision` mode section.
2. Read `MODE_REGISTRY.md` § academic-paper for mode triggers and output spec.
3. Parse the reviewer feedback provided by the user.
4. Produce:
   - A revised paper draft addressing all Critical and Major feedback items
   - A point-by-point Response-to-Reviewers document
   - A revision log tracking each feedback item (Source, Severity, Feedback, Action Taken, Status)
5. Address Minor items and viable Suggestions if a second revision round is warranted (max 2 loops).
6. Follow all citation and quality protocols.
