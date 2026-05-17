Trigger the `academic-paper` skill in `outline-only` mode. Produces a detailed paper outline and evidence map.

1. Read `academic-paper/SKILL.md` and locate the `outline-only` mode section.
2. Read `MODE_REGISTRY.md` § academic-paper for output spec.
3. Run `intake_agent` to collect: topic, paper type, RQ, citation style, word count target.
4. Run `structure_architect_agent` to build the full outline:
   - Sections and subsections with key argument per section
   - Source assignments (which sources go in which section)
   - Word count allocation per section based on paper type
5. Produce an Evidence Map: claim → source → evidence type for each major argument.
6. Present outline to user and allow adjustments before finalizing.
