---
description: ARG academic-paper format-convert mode — convert to LaTeX / DOCX / PDF / Markdown
---

Trigger the `academic-paper` skill in `format-convert` mode. Converts a paper between LaTeX, DOCX (via Pandoc), PDF, or Markdown, and converts citation styles between major formats. Fidelity spectrum, low oversight.

1. Read the skill entry at `academic-paper/SKILL.md` and locate the `format-convert` mode section.
2. Read `MODE_REGISTRY.md` § academic-paper for mode triggers and output spec.
3. Determine the source format and target format from the user's request.
4. Perform the format conversion:
   - LaTeX ↔ Markdown ↔ DOCX (via Pandoc) ↔ PDF
   - Citation style conversion between APA, Chicago, MLA, Vancouver, IEEE, etc.
5. Preserve all content, citations, and formatting semantics during conversion.
6. Output the converted document.
