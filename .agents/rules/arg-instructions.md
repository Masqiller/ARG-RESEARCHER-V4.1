# Academic Research Graphify (ARG) — Antigravity Rules

This workspace contains the ARG suite: 38 specialized AI agents across 4 skills and 26 modes for rigorous academic research, paper writing, peer review, and pipeline orchestration.

## Skills Overview

| Skill | Purpose | Modes |
|-------|---------|-------|
| `deep-research` | 13-agent research team | full, quick, socratic, review, lit-review, fact-check, systematic-review |
| `academic-paper` | 13-agent paper writing + diagram generation | full, plan, outline-only, revision, revision-coach, abstract-only, lit-review, format-convert, citation-check, disclosure, diagram |
| `academic-paper-reviewer` | 7-agent multi-perspective review | full, re-review, quick, methodology-focus, guided, calibration |
| `academic-pipeline` | 10-stage full pipeline orchestrator | (coordinates all above) |

## Slash Commands

Trigger these with `/` in the Agent Manager panel:

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
| `/arg-diagram` | Standalone structural diagram (TikZ / Mermaid / PGFPlots) |

## Intent Routing Rules

1. **Full pipeline vs individual skills**: Use `academic-pipeline` (via `/arg-full`) when the user wants research + writing + review all together. Trigger individual skills directly for single-function requests.
2. **Plan before writing**: When the user is unsure about paper structure, suggest `/arg-plan` before `/arg-full`.
3. **Diagram generation**: For standalone diagram requests ("draw a flowchart", "create an architecture diagram"), trigger `/arg-diagram`. For full papers, diagrams are generated automatically inside `/arg-full`.
4. **Robotics/AI discipline**: When discipline is Robotics, Autonomous Systems, Robot Learning, Manipulation, or HRI — `literature_strategist_agent` automatically applies the Tier 1 venue registry (T-RO, RA-L, IJRR, Science Robotics, Nature MI, ICRA, IROS, CoRL, RSS) and enforces 2021–2026 time range.
5. **Citation check**: For "check citations" or "verify references", use `/arg-citation-check` directly — do not run the full pipeline.

## Core Rules (Always Apply)

- All claims must have citations
- Evidence hierarchy respected (meta-analyses > RCTs > cohort > case reports > expert opinion)
- Contradictions disclosed with evidence quality comparison
- AI disclosure included in all outputs
- Three-layer citation protocol: format compliance → source existence → claim-faithfulness anchoring
- Default output language matches user input (English or Traditional Chinese)

## Key File Locations

| File | Purpose |
|------|---------|
| `MODE_REGISTRY.md` | Single source of truth for all 26 modes across 4 skills |
| `academic-pipeline/SKILL.md` | Full pipeline orchestrator |
| `academic-paper/SKILL.md` | Paper writing skill (13 agents) |
| `deep-research/SKILL.md` | Research skill (13 agents) |
| `academic-paper-reviewer/SKILL.md` | Review skill (7 agents) |
| `shared/handoff_schemas.md` | Material Passport + 13 handoff schemas |
| `academic-paper/agents/diagram_master_agent.md` | Diagram Master Agent (Dr. Atlas) |
| `academic-paper/agents/literature_strategist_agent.md` | Literature search with discipline-specific venue registries |
