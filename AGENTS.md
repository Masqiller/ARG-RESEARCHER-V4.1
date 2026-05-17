# AGENTS.md — ARG Researcher

Cross-tool agent instructions. Automatically loaded by Google Antigravity (v1.20.3+), Claude Code, and Cursor.

This workspace contains the **Academic Research Graphify (ARG)** suite: 38 specialized AI agents across 4 skills and 26 modes, covering the full academic research lifecycle from idea to publication.

---

## Slash Commands

| Command | What it does |
|---------|-------------|
| `/arg-full` | Full pipeline: research → write → review → revise → finalize |
| `/arg-plan` | Socratic chapter-by-chapter planning + Diagram Plan |
| `/arg-outline` | Detailed outline + evidence map |
| `/arg-abstract` | Bilingual abstract (EN + zh-TW) + keywords |
| `/arg-revision` | Revised draft + point-by-point R&R responses |
| `/arg-revision-coach` | Revision Roadmap + Response Letter Skeleton |
| `/arg-lit-review` | Annotated bibliography in paper format |
| `/arg-format-convert` | Convert to LaTeX / DOCX / PDF / Markdown |
| `/arg-citation-check` | Citation error report + auto-corrections |
| `/arg-disclosure` | Venue-specific AI-usage disclosure statement |
| `/arg-diagram` | Standalone diagram (TikZ / Mermaid / PGFPlots) |

---

## Intent Routing

- "write a paper" / "research paper" → `/arg-full`
- "plan my paper" / "chapter structure" → `/arg-plan`
- "just an outline" → `/arg-outline`
- "literature review" / "annotated bibliography" → `/arg-lit-review`
- "write abstract" → `/arg-abstract`
- "revise paper" / "reviewer comments" → `/arg-revision`
- "parse reviews" / "coaching on response" → `/arg-revision-coach`
- "check citations" / "verify references" → `/arg-citation-check`
- "convert to LaTeX" / "export DOCX" → `/arg-format-convert`
- "AI disclosure" → `/arg-disclosure`
- "generate diagram" / "draw a flowchart" → `/arg-diagram`

---

## Core Rules

- Every claim must have a citation
- Three-layer citation protocol: format → source existence → claim-faithfulness anchoring
- Evidence hierarchy: meta-analyses > RCTs > cohort > case reports > expert opinion
- AI disclosure included in all outputs
- Default language matches user input (English or Traditional Chinese)
- For Robotics/AI papers: apply Tier 1 venue registry (T-RO, RA-L, IJRR, Science Robotics, ICRA, IROS, CoRL, RSS), enforce 2021–2026 time range

---

## Key Files

| File | Purpose |
|------|---------|
| `MODE_REGISTRY.md` | All 26 modes across 4 skills |
| `academic-pipeline/SKILL.md` | Full pipeline orchestrator |
| `academic-paper/SKILL.md` | Paper writing (13 agents) |
| `deep-research/SKILL.md` | Research (13 agents) |
| `academic-paper-reviewer/SKILL.md` | Review (7 agents) |
| `shared/handoff_schemas.md` | Handoff schemas (13 schemas) |
