# Quick Start

Get from zero to your first AI-assisted research in 3 steps.

> **Multi-agent support**: ARG works with Claude Code, Windsurf, Cursor, GitHub Copilot, Cline/Roo Code, Aider, Continue, and any other AI agent. See [UNIVERSAL_SETUP.md](UNIVERSAL_SETUP.md) for agent-specific setup instructions.

## Step 1: Install

```bash
# Clone this repo somewhere stable
git clone https://github.com/Masqiller/ARG-Researcher.git ~/ARG-Researcher
```

### Claude Code (original setup)

```bash
# Install Claude Code
curl -fsSL https://claude.ai/install.sh | bash

# Install each of the four skills into your project's .claude/skills/
cd /path/to/your/project
mkdir -p .claude/skills
ln -s ~/ARG-Researcher/deep-research .claude/skills/deep-research
ln -s ~/ARG-Researcher/academic-paper .claude/skills/academic-paper
ln -s ~/ARG-Researcher/academic-paper-reviewer .claude/skills/academic-paper-reviewer
ln -s ~/ARG-Researcher/academic-pipeline .claude/skills/academic-pipeline
```

Each skill must sit at `.claude/skills/<skill-name>/SKILL.md` for Claude Code to discover it. See [docs/SETUP.md](docs/SETUP.md) for the copy-based alternative (Option B) and other installation methods (global `~/.claude/skills/`, Cowork, claude.ai).

### Other Agents (Windsurf, Cursor, Copilot, Cline, etc.)

Simply open the cloned repo in your IDE — agent-specific config files are auto-discovered:
- **Windsurf**: `.windsurf/workflows/arg-*.md` (10 native slash commands)
- **Cursor**: `.cursor/rules/arg-instructions.mdc` (auto-loaded rules)
- **GitHub Copilot**: `.github/copilot-instructions.md`
- **Cline / Roo Code**: `.clinerules`
- **Continue**: `.continue/config.json`
- **Aider**: `.aider/conventions.md`
- **Any agent**: `.ai/instructions.md` (universal instructions)

See [UNIVERSAL_SETUP.md](UNIVERSAL_SETUP.md) for detailed per-agent instructions including how to use ARG in a different project.

## Step 2: Launch

```bash
# Claude Code
claude

# Other agents: just open the repo in your IDE
```

## Step 3: Start researching

Tell your AI agent what you want to do. It will automatically pick the right skill and mode.

### Example: Guided research (Socratic mode)

```
You: "I have a vague idea about AI's impact on higher education quality assurance,
      but I'm not sure how to frame the research question. Can you guide me?"
```

The agent will enter Socratic mode — asking questions to help you clarify your thinking, not giving you answers directly. After 5-15 rounds of dialogue, you'll have a focused research question and methodology direction.

### Example: Write a paper

```
You: "Help me write a paper about the impact of declining birth rates
      on private universities in Taiwan"
```

### Example: Review an existing paper

```
You: "Review this paper" (then paste or attach the paper)
```

### Example: Full pipeline (research → write → review → revise → publish)

```
You: "I want to produce a complete research paper about how agentic AI
      is reshaping student learning outcome measurement"
```

This triggers the full 10-stage pipeline. Budget ~$4-6 in API costs and 2-4 hours of collaborative work.

## Which mode should I use?

| I want to... | Use this |
|-------------|----------|
| Explore a vague idea | `deep-research` socratic mode — just describe your interest |
| Get a quick literature summary | `deep-research` quick mode |
| Do a systematic review (PRISMA) | `deep-research` systematic-review mode |
| Write a paper from scratch | `academic-paper` full mode |
| Plan a paper chapter by chapter | `academic-paper` plan mode |
| Get my paper reviewed | `academic-paper-reviewer` full mode |
| Do everything end-to-end | `academic-pipeline` — say "I want a complete research paper" |

## What's next?

- [Full README](README.md) — all features, modes, installation options, and changelog
- [UNIVERSAL_SETUP.md](UNIVERSAL_SETUP.md) — detailed per-agent setup instructions
- [中文版](README.zh-TW.md) — Traditional Chinese version
- [Pipeline showcase](examples/showcase/) — real artifacts from a complete pipeline run
