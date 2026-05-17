# Universal Agent Setup Guide

ARG works with **any** AI coding agent. This guide covers setup for each supported agent platform.

---

## Quick Summary

| Agent | Config File(s) | Slash Commands Via |
|-------|----------------|-------------------|
| **Claude Code** | `.claude/CLAUDE.md` + `commands/arg-*.md` | Native slash commands (`/arg-full`, etc.) |
| **Windsurf (Cascade)** | `.windsurf/workflows/arg-*.md` | Native workflows (`/arg-full`, etc.) |
| **Google Antigravity** | `.agents/rules/arg-instructions.md` + `.agents/workflows/arg-*.md` | Native `/arg-*` slash commands in Agent Manager |
| **Cursor** | `.cursor/rules/arg-instructions.mdc` | Mention `/arg-*` in chat — rules auto-load |
| **GitHub Copilot** | `.github/copilot-instructions.md` | Mention `/arg-*` in chat |
| **Cline / Roo Code** | `.clinerules` | Mention `/arg-*` in chat |
| **Aider** | `.aider/conventions.md` | Mention `/arg-*` in chat |
| **Continue** | `.continue/config.json` | Mention `/arg-*` in chat |
| **Any other agent** | `.ai/instructions.md` | Mention `/arg-*` in chat |

---

## Step 1: Clone the Repo

```bash
git clone https://github.com/Masqiller/ARG-Researcher.git ~/ARG-Researcher
```

## Step 2: Agent-Specific Setup

### Claude Code (Original)

```bash
# Option A: Plugin install (if available)
# /plugin install ARG-Researcher

# Option B: Symlink skills into your project
cd /path/to/your/project
mkdir -p .claude/skills
ln -s ~/ARG-Researcher/deep-research .claude/skills/deep-research
ln -s ~/ARG-Researcher/academic-paper .claude/skills/academic-paper
ln -s ~/ARG-Researcher/academic-paper-reviewer .claude/skills/academic-paper-reviewer
ln -s ~/ARG-Researcher/academic-pipeline .claude/skills/academic-pipeline
```

Slash commands are natively available as `/arg-full`, `/arg-plan`, etc.

See [QUICKSTART.md](QUICKSTART.md) and [docs/SETUP.md](docs/SETUP.md) for more options.

---

### Google Antigravity

**No extra setup needed** if you open this repo in Antigravity. The `.agents/` directory is auto-discovered:
- `.agents/rules/arg-instructions.md` — always-on rules (auto-loaded for every session)
- `.agents/workflows/arg-*.md` — 12 native slash commands available via `/` in the Agent Manager panel

Also, `AGENTS.md` in the project root is loaded automatically (cross-tool format, Antigravity v1.20.3+).

To use ARG in a **different project**, copy both directories:

```bash
cd /path/to/your/project
mkdir -p .agents/rules .agents/workflows
cp ~/ARG-Researcher/.agents/rules/arg-instructions.md .agents/rules/
cp ~/ARG-Researcher/.agents/workflows/arg-*.md .agents/workflows/
cp ~/ARG-Researcher/AGENTS.md .
```

All 12 slash commands (`/arg-full`, `/arg-plan`, `/arg-diagram`, etc.) will be available in the Agent Manager panel.

---

### Windsurf (Cascade)

**No extra setup needed** if you open this repo in Windsurf. The `.windsurf/workflows/` directory is auto-discovered.

To use ARG in a **different project**, symlink or copy the workflows:

```bash
cd /path/to/your/project
mkdir -p .windsurf/workflows
ln -s ~/ARG-Researcher/.windsurf/workflows/arg-*.md .windsurf/workflows/
```

All 10 slash commands (`/arg-full`, `/arg-plan`, etc.) are available as native Windsurf workflows.

---

### Cursor

**No extra setup needed** if you open this repo in Cursor. The `.cursor/rules/` directory is auto-discovered.

To use ARG in a **different project**, copy the rules file:

```bash
cd /path/to/your/project
mkdir -p .cursor/rules
cp ~/ARG-Researcher/.cursor/rules/arg-instructions.mdc .cursor/rules/
```

Then mention `/arg-full`, `/arg-plan`, etc. in chat — the agent knows what to do.

---

### GitHub Copilot

**No extra setup needed** if you open this repo in VS Code with Copilot. The `.github/copilot-instructions.md` file is auto-discovered.

To use ARG in a **different project**, copy the instructions:

```bash
cd /path/to/your/project
mkdir -p .github
cp ~/ARG-Researcher/.github/copilot-instructions.md .github/
```

---

### Cline / Roo Code

**No extra setup needed** if you open this repo. The `.clinerules` file is auto-discovered.

To use ARG in a **different project**:

```bash
cp ~/ARG-Researcher/.clinerules /path/to/your/project/
```

---

### Aider

Add the conventions file to Aider's read list:

```bash
cd /path/to/your/project
mkdir -p .aider
cp ~/ARG-Researcher/.aider/conventions.md .aider/
```

Then start Aider with: `aider --read .aider/conventions.md`

Or reference the full instructions: `aider --read ~/ARG-Researcher/.ai/instructions.md`

---

### Continue

**No extra setup needed** if you open this repo. The `.continue/config.json` is auto-discovered.

To use ARG in a **different project**:

```bash
cd /path/to/your/project
mkdir -p .continue
cp ~/ARG-Researcher/.continue/config.json .continue/
```

---

### Any Other Agent

The universal instructions file at `.ai/instructions.md` works with any agent that supports project-level instructions. Either:

1. **Point your agent to the file**: Configure your agent to read `.ai/instructions.md` as system context.
2. **Copy-paste**: Open `.ai/instructions.md` and paste it into your agent's system prompt or custom instructions.

---

## Step 3: Start Using ARG

Tell your agent what you want. It will use the ARG skills and modes automatically:

| I want to... | Say this |
|-------------|----------|
| Explore a vague research idea | "Guide my research on [topic]" or `/arg-plan` |
| Get a quick literature summary | "Quick research on [topic]" |
| Write a paper from scratch | "Write a paper about [topic]" or `/arg-full` |
| Plan a paper chapter by chapter | `/arg-plan` |
| Get an outline only | `/arg-outline` |
| Review an existing paper | "Review this paper" (paste/attach) |
| Revise based on reviewer comments | `/arg-revision` |
| Get coaching on reviewer responses | `/arg-revision-coach` |
| Generate a bilingual abstract | `/arg-abstract` |
| Write a literature review | `/arg-lit-review` |
| Convert paper format | `/arg-format-convert` |
| Check citations | `/arg-citation-check` |
| Generate AI-usage disclosure | `/arg-disclosure` |
| Do everything end-to-end | `/arg-full` |

---

## File Structure Reference

```
ARG-Researcher/
├── .agents/rules/arg-instructions.md   # Antigravity always-on rules
├── .agents/workflows/arg-*.md          # Antigravity slash command workflows
├── AGENTS.md                           # Cross-tool root file (Antigravity + Cursor + Claude Code)
├── .ai/instructions.md                 # Universal agent instructions
├── .aider/conventions.md            # Aider conventions
├── .claude/CLAUDE.md                # Claude Code instructions
├── .claude-plugin/                  # Claude Code plugin metadata
├── .clinerules                      # Cline / Roo Code rules
├── .continue/config.json            # Continue config
├── .cursor/rules/arg-instructions.mdc  # Cursor rules
├── .github/copilot-instructions.md  # GitHub Copilot instructions
├── .windsurf/workflows/arg-*.md     # Windsurf slash command workflows
├── commands/arg-*.md                # Claude Code slash commands
├── agents/                          # Plugin-shipped agents
├── academic-paper/                  # Paper writing skill
├── academic-paper-reviewer/         # Review skill
├── academic-pipeline/               # Pipeline orchestrator
├── deep-research/                   # Research skill
├── shared/                          # Shared schemas, templates, references
├── MODE_REGISTRY.md                 # Single source of truth for all modes
├── QUICKSTART.md                    # Quick start guide
└── UNIVERSAL_SETUP.md               # This file
```
