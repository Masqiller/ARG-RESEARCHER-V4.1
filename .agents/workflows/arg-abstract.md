Trigger the `academic-paper` skill in `abstract-only` mode. Produces a bilingual abstract (EN + zh-TW) and keywords.

1. Read `academic-paper/SKILL.md` and locate the `abstract-only` mode section.
2. Read `MODE_REGISTRY.md` § academic-paper for output spec.
3. Ask the user to provide: completed paper draft or detailed outline + key findings.
4. Run `abstract_bilingual_agent` to produce:
   - Structured abstract: Background → Gap → Objective → Method → Results → Conclusion → Implications
   - English version following APA 7.0 abstract conventions
   - Traditional Chinese (zh-TW) version
   - 5–8 keywords in both languages
5. Present both versions for user review.
