# Academic Research Graphify (ARG) — Aider Conventions

## Repository Purpose

This is the ARG suite — a production-grade academic research pipeline with 4 skills (deep-research, academic-paper, academic-paper-reviewer, academic-pipeline), 25 modes, and 32+ agents.

## Key Conventions

- `MODE_REGISTRY.md` is the single source of truth for all modes — update it first when adding/modifying modes.
- Agent definitions live in `agents/` (plugin-shipped) and within each skill's `agents/` directory.
- Agents use `model: inherit` in frontmatter — they adapt to whatever model is running.
- All outputs must include AI disclosure statements.
- All claims must have citations following the evidence hierarchy.
- Citation emission follows Two-Layer (v3.7.1) and Three-Layer (v3.7.3) protocols.
- Material Passport in `shared/handoff_schemas.md` governs inter-stage handoffs.
- Tests live in `tests/` with scripts in `scripts/`.
- CI workflows in `.github/workflows/spec-consistency.yml`.

## Slash Commands

The repo provides 10 slash commands (arg-full, arg-plan, arg-outline, arg-abstract, arg-revision, arg-revision-coach, arg-lit-review, arg-format-convert, arg-citation-check, arg-disclosure) defined in multiple agent formats:
- Claude Code: `commands/arg-*.md`
- Windsurf: `.windsurf/workflows/arg-*.md`
- Cursor: `.cursor/rules/arg-instructions.mdc`
- Generic: `.ai/instructions.md`
