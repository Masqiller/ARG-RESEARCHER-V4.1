# Academic Research Graphify (ARG) — Universal Agent Instructions

A suite of AI-assisted skills for rigorous academic research, paper writing, peer review, and pipeline orchestration. This file provides context for **any** AI coding agent operating in this repository.

## Skills Overview

| Skill | Purpose | Key Modes |
|-------|---------|-----------|
| `deep-research` v2.9.3 | 13-agent research team | full, quick, socratic, review, lit-review, fact-check, systematic-review |
| `academic-paper` v3.1.1 | 12-agent paper writing | full, plan, outline-only, revision, revision-coach, abstract-only, lit-review, format-convert, citation-check, disclosure |
| `academic-paper-reviewer` v1.9.0 | Multi-perspective paper review (5 reviewers + optional cross-model DA critique) | full, re-review, quick, methodology-focus, guided, calibration |
| `academic-pipeline` v3.7.0 | Full pipeline orchestrator | (coordinates all above) |

## Available Slash Commands / Workflows

These 10 commands map to specific ARG modes. Depending on your agent, they may be available as slash commands, workflows, or manual triggers.

| Command | Mode | Description |
|---------|------|-------------|
| `/arg-full` | pipeline | Full pipeline: research → write → review → revise → finalize |
| `/arg-plan` | academic-paper plan | Socratic chapter-by-chapter planning |
| `/arg-outline` | academic-paper outline-only | Detailed outline + evidence map |
| `/arg-abstract` | academic-paper abstract-only | Bilingual abstract (zh-TW + EN) + keywords |
| `/arg-revision` | academic-paper revision | Revised draft + R&R responses |
| `/arg-revision-coach` | academic-paper revision-coach | Revision Roadmap + Response Letter skeleton |
| `/arg-lit-review` | academic-paper lit-review | Annotated bibliography in paper format |
| `/arg-format-convert` | academic-paper format-convert | Convert to LaTeX / DOCX / PDF / Markdown |
| `/arg-citation-check` | academic-paper citation-check | Citation error report |
| `/arg-disclosure` | academic-paper disclosure | Venue-specific AI-usage statement |

## Routing Rules

1. **academic-pipeline vs individual skills**: academic-pipeline = full pipeline orchestrator (research → write → integrity → review → revise → final integrity → finalize). If the user only needs a single function (just research, just write, just review), trigger the corresponding skill directly without the pipeline.

2. **deep-research vs academic-paper**: Complementary. deep-research = upstream research engine (investigation + fact-checking), academic-paper = downstream publication engine (paper writing + bilingual abstracts). Recommended flow: deep-research → academic-paper.

3. **deep-research socratic vs full**: socratic = guided Socratic dialogue to help users clarify their research question. full = direct production of research report. When the user's research question is unclear, suggest socratic mode.

4. **academic-paper plan vs full**: plan = chapter-by-chapter guided planning via Socratic dialogue. full = direct paper production. When the user wants to think through their paper structure, suggest plan mode.

5. **academic-paper-reviewer guided vs full**: guided = Socratic review that engages the author in dialogue about issues. full = standard multi-perspective review report. When the user wants to learn from the review, suggest guided mode.

## Key Rules

- All claims must have citations
- Evidence hierarchy respected (meta-analyses > RCTs > cohort > case reports > expert opinion)
- Contradictions disclosed with evidence quality comparison
- AI disclosure in all reports
- Default output language matches user input (Traditional Chinese or English)

## Full Academic Pipeline

```
deep-research (socratic/full)
  → academic-paper (plan/full)
    → integrity check (Stage 2.5)
      → academic-paper-reviewer (full/guided)
        → academic-paper (revision)
          → academic-paper-reviewer (re-review, max 2 loops)
            → final integrity check (Stage 4.5)
              → academic-paper (format-convert → final output)
                → Process Summary + AI Self-Reflection Report
```

## Handoff Protocol

### deep-research → academic-paper
Materials: RQ Brief, Methodology Blueprint, Annotated Bibliography, Synthesis Report, INSIGHT Collection

### academic-paper → academic-paper-reviewer
Materials: Complete paper text. field_analyst_agent auto-detects domain and configures reviewers.

### academic-paper-reviewer → academic-paper (revision)
Materials: Editorial Decision Letter, Revision Roadmap, Per-reviewer detailed comments

## Key File Locations

| File | Purpose |
|------|---------|
| `MODE_REGISTRY.md` | Single source of truth for all 25 modes across 4 skills |
| `academic-pipeline/SKILL.md` | Pipeline orchestrator skill definition |
| `academic-paper/SKILL.md` | Paper writing skill definition |
| `deep-research/SKILL.md` | Research skill definition |
| `academic-paper-reviewer/SKILL.md` | Review skill definition |
| `shared/handoff_schemas.md` | Material Passport handoff schema |
| `agents/*.md` | Plugin-shipped agent definitions |
| `docs/PERFORMANCE.md` | Token budget and performance guidance |

## Agent Definitions

Three plugin-shipped agents (in `agents/`):
- **synthesis_agent** — Cross-source integration, contradiction resolution, gap analysis
- **research_architect_agent** — Methodology blueprint (paradigm, method, data strategy)
- **report_compiler_agent** — APA 7.0 report drafting (Phase 4 + Phase 6)

Other agents (bibliography_agent, literature_strategist_agent, field_analyst_agent, etc.) are in-skill prompt templates loaded via their respective SKILL.md files.

## Version Info
- **Suite version**: 3.7.0
- **Last Updated**: 2026-05-05
- **Attribution**: See CONTRIBUTORS.md
- **License**: MIT
