Trigger the `academic-paper` skill in `plan` mode. Produces a Chapter Plan + INSIGHT collection through Socratic dialogue, then generates a Diagram Plan.

1. Read the skill entry at `academic-paper/SKILL.md` and locate the `plan` mode section.
2. Read `MODE_REGISTRY.md` § academic-paper for mode triggers and output spec.
3. Engage the user in Socratic dialogue to plan each chapter:
   - Ask clarifying questions about the research topic, scope, and audience.
   - Guide the user through chapter-by-chapter planning decisions.
   - Collect INSIGHTs along the way.
4. After chapter planning completes, invoke `diagram_master_agent` in Planner mode:
   - Read `academic-paper/agents/diagram_master_agent.md` for Dr. Atlas's Planner sub-role.
   - Read `academic-paper/references/diagram_taxonomy.md` for detection heuristics.
   - Scan the completed Chapter Plan for diagram opportunities (Categories 1–13).
   - Score each opportunity (1–5 necessity scale) and apply suppression rules.
   - Present the Diagram Plan table to the user for confirmation; allow adjustments.
5. Produce a Chapter Plan with evidence mapping.
6. Produce an INSIGHT collection summarizing key decisions made during planning.
7. Produce a confirmed Diagram Plan artifact (using `academic-paper/templates/diagram_plan_template.md`).
8. Follow all key rules from the skill: citations required, evidence hierarchy respected, AI disclosure included.
