Trigger the `academic-paper` skill in `revision` mode. Produces a revised draft and formal Response to Reviewers letter.

1. Read `academic-paper/SKILL.md` and locate the `revision` mode section.
2. Read `MODE_REGISTRY.md` § academic-paper for output spec.
3. Ask the user to provide: original paper draft + reviewer comments.
4. Run `revision_coach_agent` to:
   - Categorize every reviewer comment by severity: Critical / Major / Minor / Suggestion
   - Build a Revision Roadmap mapping each comment to a specific action and section
5. Run `draft_writer_agent` to execute revisions:
   - All Critical and Major items must be addressed
   - Minor items addressed within word count constraints
   - Every change logged in a Revision Log (item → section → action → status)
6. Produce a formal Response to Reviewers letter with point-by-point responses.
7. Output: Revised draft + Revision Log + Response to Reviewers letter.
