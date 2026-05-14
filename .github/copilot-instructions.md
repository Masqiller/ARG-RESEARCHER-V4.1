# Academic Research Graphify (ARG) — GitHub Copilot Instructions

This repository contains the Academic Research Graphify (ARG) suite — a production-grade academic research pipeline with 4 skills, 25 modes, and 32+ agents.

## What This Repo Does

ARG orchestrates a complete academic research workflow: **research → write → review → revise → finalize**. It ships 4 skills:
- `deep-research` — 13-agent research team (literature search, synthesis, fact-checking)
- `academic-paper` — 12-agent paper writing (IMRaD structure, revision, format conversion)
- `academic-paper-reviewer` — Multi-perspective peer review (5 reviewers + editorial synthesis)
- `academic-pipeline` — Full pipeline orchestrator coordinating all above

## Key Commands (Slash Commands)

When the user mentions any of these, read the corresponding `SKILL.md` and execute:

| Command | Skill + Mode | Output |
|---------|-------------|--------|
| `/arg-full` | academic-pipeline | Complete 10-stage pipeline |
| `/arg-plan` | academic-paper plan | Chapter Plan via Socratic dialogue |
| `/arg-outline` | academic-paper outline-only | Outline + evidence map |
| `/arg-abstract` | academic-paper abstract-only | Bilingual abstract + keywords |
| `/arg-revision` | academic-paper revision | Revised draft + R&R responses |
| `/arg-revision-coach` | academic-paper revision-coach | Revision Roadmap + Response Letter skeleton |
| `/arg-lit-review` | academic-paper lit-review | Annotated bibliography |
| `/arg-format-convert` | academic-paper format-convert | LaTeX / DOCX / PDF / Markdown conversion |
| `/arg-citation-check` | academic-paper citation-check | Citation error report |
| `/arg-disclosure` | academic-paper disclosure | AI-usage disclosure statement |

## Rules for This Codebase

- All claims must have citations; evidence hierarchy is enforced
- AI disclosure is mandatory in all reports
- The `MODE_REGISTRY.md` file is the single source of truth for all modes
- Agent definitions in `agents/` use `model: inherit` — they adapt to whatever model the user is running
- Default output language matches user input (Traditional Chinese or English)
- Read `shared/handoff_schemas.md` for Material Passport protocol between pipeline stages
