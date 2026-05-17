Trigger the `academic-paper` skill in `revision-coach` mode. Produces a Revision Roadmap and Response Letter Skeleton without rewriting the paper.

1. Read `academic-paper/SKILL.md` and locate the `revision-coach` mode section.
2. Read `MODE_REGISTRY.md` § academic-paper for output spec.
3. Ask the user to provide their reviewer comments.
4. Run `revision_coach_agent` to:
   - Read and categorize every comment (Critical / Major / Minor / Suggestion)
   - Identify the underlying issue behind each comment, not just the surface request
   - Map every comment to a specific section and action
5. Produce a Revision Roadmap: what to fix, where, and how — for each comment.
6. Produce a Response Letter Skeleton with suggested tone and framing for each response point.
7. Do NOT rewrite the paper — the user writes the revision guided by the roadmap.
