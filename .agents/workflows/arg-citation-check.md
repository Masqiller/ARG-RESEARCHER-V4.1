Trigger the `academic-paper` skill in `citation-check` mode. Audits all citations and auto-corrects errors.

1. Read `academic-paper/SKILL.md` and locate the `citation-check` mode section.
2. Read `MODE_REGISTRY.md` § academic-paper for output spec.
3. Ask the user to provide their paper draft with in-text citations and reference list.
4. Run `citation_compliance_agent`:
   - Build a Citation Index from all in-text citations and the reference list
   - Zero-orphan check: every in-text citation must appear in the reference list and vice versa
   - Format compliance: check all APA/IEEE/Chicago/MLA/Vancouver rules for the selected style
   - DOI check: verify `https://doi.org/...` format, flag missing DOIs
   - Auto-correct deterministic errors (wrong `&` vs `and`, wrong ordering, wrong DOI format, etc.)
   - Flag ambiguous cases for human review
   - Self-citation ratio check (flag if > 15%)
   - Source currency check (flag sources older than 10 years unless seminal)
   - For Robotics/AI: currency threshold is 5 years; pre-2018 sources must be tagged seminal
5. Output: Citation Audit Report + corrected reference list.
