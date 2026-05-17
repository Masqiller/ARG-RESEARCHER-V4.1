Trigger the `academic-paper` skill in `disclosure` mode. Generates a venue-specific AI usage disclosure statement.

1. Read `academic-paper/SKILL.md` and locate the `disclosure` mode section.
2. Read `MODE_REGISTRY.md` § academic-paper for output spec.
3. Ask the user for their target venue (journal or conference name).
4. Look up the venue's AI disclosure policy requirements.
5. Generate a disclosure statement that:
   - Matches the venue's required format and scope
   - Specifies exactly which parts of the workflow used AI assistance
   - Is formatted for direct insertion into the manuscript
6. Output: venue-formatted AI disclosure statement.
