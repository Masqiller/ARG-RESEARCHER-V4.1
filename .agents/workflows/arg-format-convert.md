Trigger the `academic-paper` skill in `format-convert` mode. Converts a paper draft to LaTeX, DOCX, PDF, or Markdown.

1. Read `academic-paper/SKILL.md` and locate the `format-convert` mode section.
2. Read `MODE_REGISTRY.md` § academic-paper for output spec.
3. Ask the user to provide: paper draft, target format, and target journal/style (optional).
4. Run `formatter_agent`:
   - For LaTeX: generate `.tex` + `.bib`, inject correct preamble packages, apply journal template if specified
   - For DOCX: run Pandoc conversion with APA/journal style template
   - For PDF: compile via tectonic (LaTeX → PDF)
   - For Markdown: clean and structure as `.md`
5. Convert citation format to match the target style (e.g., author-date → numbered IEEE).
6. Output the formatted document.
