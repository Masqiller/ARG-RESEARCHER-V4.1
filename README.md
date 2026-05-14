<div align="center">

# Academic Research Graphify (ARG)

**Your AI-powered academic research copilot**

[![Version](https://img.shields.io/badge/version-v4.0.0-blue)](#)
[![License: MIT](https://img.shields.io/badge/license-MIT-green)](https://opensource.org/licenses/MIT)
[![Agents](https://img.shields.io/badge/agents-37-purple)](#-the-agent-team)
[![Skills](https://img.shields.io/badge/skills-4-orange)](#-skills--modes)
[![Modes](https://img.shields.io/badge/modes-25-red)](#-skills--modes)

[繁體中文](README.zh-TW.md) | [Español](README.es.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [Português](README.pt-BR.md) | [हिन्दी](README.hi.md) | [العربية](README.ar.md) | [Русский](README.ru.md)

---

**37 specialized AI agents** working across **4 skills** and **25 modes** to take your research from idea to publication.
Works with **any AI coding agent** — Windsurf, Cursor, Claude Code, GitHub Copilot, Cline, Aider, Continue, and more.

[Get Started](#-quick-start) | [Features](#-features) | [Architecture](docs/ARCHITECTURE.md) | [Setup Guide](UNIVERSAL_SETUP.md)

</div>

---

## Why ARG?

> **AI is your copilot, not the pilot.** ARG doesn't write your paper for you. It handles the grunt work — hunting down references, formatting citations, verifying data, checking logical consistency — so you can focus on what actually requires your brain: defining the question, choosing the method, interpreting the data, and writing the sentence after *"I argue that..."*

Fully autonomous AI research pipelines inherit structural failure modes: hallucinated results, methodology fabrication, frame-lock, citation hallucinations. **These are not bugs — they're architectural.** No amount of scaling eliminates them.

ARG is built on one premise: **a human researcher + AI avoids these failure modes better than either alone.**

| Problem | ARG's Solution |
|---------|---------------|
| Citation hallucinations | Semantic Scholar API verification + integrity gates |
| Frame-lock | Devil's Advocate with concession threshold protocol |
| Sycophancy | Anti-sycophancy scoring (1-5 scale before any concession) |
| Premature convergence | Intent detection + dialogue health monitoring |
| Methodology fabrication | 7-mode blocking checklist at Stage 2.5 & 4.5 |
| Unverifiable claims | Three-layer citation protocol + claim-faithfulness anchoring |

---

## Quick Start

```bash
git clone https://github.com/Masqiller/ARG-Researcher.git ~/ARG-Researcher
```

Open the repo in your IDE. Config files are auto-discovered:

| Agent | Config | Commands |
|:------|:-------|:---------|
| **Windsurf** | `.windsurf/workflows/arg-*.md` | Native `/arg-*` workflows |
| **Cursor** | `.cursor/rules/arg-instructions.mdc` | `/arg-*` in chat |
| **Claude Code** | `.claude/CLAUDE.md` + `commands/` | Native `/arg-*` commands |
| **GitHub Copilot** | `.github/copilot-instructions.md` | `/arg-*` in chat |
| **Cline / Roo Code** | `.clinerules` | `/arg-*` in chat |
| **Aider** | `.aider/conventions.md` | `/arg-*` in chat |
| **Continue** | `.continue/config.json` | `/arg-*` in chat |
| **Any other** | `.ai/instructions.md` | `/arg-*` in chat |

**Test it:** Run `/arg-plan` and describe a paper you're working on. ARG starts a Socratic dialogue to map out your chapter structure.

> **Detailed setup:** [UNIVERSAL_SETUP.md](UNIVERSAL_SETUP.md) | **Full config guide:** [docs/SETUP.md](docs/SETUP.md)
>
> *Optional dependencies:* Pandoc (DOCX export), tectonic (PDF/LaTeX). Markdown output works without either.

---

## Features

<table>
<tr>
<td width="50%">

### Deep Research
*13 agents | 7 modes*

- Socratic guided exploration
- PRISMA systematic review
- Semantic Scholar API verification
- Intent detection (exploratory vs. goal-oriented)
- Dialogue health monitoring
- Cross-model Devil's Advocate (optional)
- Fact-checking with evidence hierarchy

</td>
<td width="50%">

### Academic Paper
*12 agents | 10 modes*

- Style Calibration (learns your voice)
- Writing Quality Check
- LaTeX hardening (APA 7.0, IEEE, Chicago)
- Visualization agent (matplotlib/seaborn/ggplot2)
- Revision coaching & R&R response
- Citation format conversion (5 formats)
- Anti-leakage protocol
- VLM figure verification

</td>
</tr>
<tr>
<td width="50%">

### Academic Paper Reviewer
*7 agents | 6 modes*

- EIC + 3 dynamic reviewers + Devil's Advocate
- 0-100 quality rubrics per dimension
- Sprint Contract (paper-blind Phase 1 + Phase 2)
- Concession threshold protocol
- Calibration mode (measure FNR/FPR)
- R&R traceability matrix

</td>
<td width="50%">

### Academic Pipeline
*10-stage orchestrator*

- Adaptive checkpoints with user confirmation
- Integrity gates at Stage 2.5 & 4.5 (mandatory, cannot be skipped)
- Material Passport with claim verification
- Collaboration Depth Observer (advisory)
- Score trajectory tracking
- 6-dimension collaboration evaluation (1-100)

</td>
</tr>
</table>

---

## The Agent Team

ARG deploys **37 specialized agents**, each with a named persona:

<details>
<summary><strong>Deep Research Agents (13)</strong></summary>

| Agent | Persona | Role |
|:------|:--------|:-----|
| Research Question Architect | Dr. Emile Fournier | Transforms vague topics into precise, researchable questions |
| Research Architect | Dr. Yuki Tanaka | Designs methodological blueprints (paradigm, method, data strategy) |
| Bibliography Agent | Dr. Carlos Mendoza | Systematic literature search & APA 7.0 curation |
| Source Verification | Dr. Fatima Al-Rashid | Evidence hierarchy grading, predatory pub detection |
| Synthesis Agent | Dr. Henrik Larsson | Cross-source integration, contradiction resolution |
| Report Compiler | Dr. Mei-Ling Chen | APA 7.0 report drafting |
| Editor-in-Chief | Dr. Oluwaseun Adeyemi | Q1 journal editorial review & verdict |
| Devil's Advocate | Dr. Sofia Petrova | Assumption challenger & bias hunter |
| Ethics Review | Dr. Kwame Asante | Final ethics gate before delivery |
| Socratic Mentor | Dr. Isabella Rossi | Guided research thinking via Socratic questioning |
| Risk of Bias | Dr. Lars Johansson | RoB 2 / ROBINS-I bias assessment |
| Meta-Analysis | Dr. Amara Okonkwo | Effect sizes, forest plots, GRADE framework |
| Monitoring Agent | Dr. Jin-Soo Park | Post-research literature monitoring |

</details>

<details>
<summary><strong>Academic Paper Agents (12)</strong></summary>

| Agent | Persona | Role |
|:------|:--------|:-----|
| Intake Agent | Dr. Smit | Paper configuration interview |
| Literature Strategist | Dr. Mridankan | Search strategy & source selection |
| Structure Architect | Dr. Aditya | Paper structure design |
| Argument Builder | Dr. Arvind | Logical argument construction |
| Draft Writer | Dr. Kavya | Academic prose drafting |
| Citation Compliance | Dr. Rohan | Citation format verification |
| Abstract Bilingual | Dr. Priya | Bilingual abstract composition |
| Peer Reviewer | Dr. Vikram | Simulated peer review |
| Formatter | Dr. Neha | Output format conversion |
| Socratic Mentor | Dr. Arjun | Chapter-by-chapter planning |
| Visualization | Dr. Meera | Publication-quality figures |
| Revision Coach | Dr. Ishaan | Reviewer comment parsing & roadmap |

</details>

<details>
<summary><strong>Paper Reviewer Agents (7)</strong></summary>

| Agent | Persona | Role |
|:------|:--------|:-----|
| Field Analyst | Dr. Tanvi | Paper field identification & team config |
| Editor-in-Chief | Dr. Rajan | Editorial decision & panel orchestration |
| Methodology Reviewer | Dr. Ananya | Research methodology assessment |
| Domain Reviewer | Dr. Karthik | Field-specific expertise review |
| Perspective Reviewer | Dr. Divya | Cross-disciplinary evaluation |
| Devil's Advocate | Dr. Sanjay | Stress-testing & vulnerability analysis |
| Editorial Synthesizer | Dr. Nandini | Review consolidation & revision roadmap |

</details>

<details>
<summary><strong>Pipeline & Shared Agents (5)</strong></summary>

| Agent | Persona | Role |
|:------|:--------|:-----|
| Pipeline Orchestrator | Dr. Rajesh | Multi-skill handoff coordination |
| Integrity Verification | Dr. Lakshmi | Reference & data verification |
| Collaboration Depth | Dr. Farhan | Collaboration quality observation |
| State Tracker | Dr. Pooja | Pipeline state & progress dashboard |
| Compliance Agent | Dr. Elena Vasquez | PRISMA-trAIce + RAISE checks |

</details>

---

## Skills & Modes

### `/arg-*` Slash Commands

| Command | What it does |
|:--------|:-------------|
| `/arg-full` | Full pipeline: research → write → review → revise → finalize |
| `/arg-plan` | Socratic chapter-by-chapter planning |
| `/arg-outline` | Detailed outline + evidence map |
| `/arg-abstract` | Bilingual abstract (ZH-TW + EN) + keywords |
| `/arg-revision` | Revised draft + R&R responses |
| `/arg-revision-coach` | Revision roadmap + response letter skeleton |
| `/arg-lit-review` | Annotated bibliography in paper format |
| `/arg-format-convert` | Convert to LaTeX / DOCX / PDF / Markdown |
| `/arg-citation-check` | Citation error report |
| `/arg-disclosure` | Venue-specific AI-usage statement |

### Natural Language Activation

You don't need slash commands. Just describe what you need:

```
"I want to write a research paper on AI's impact on higher education"
  → Full pipeline from Stage 1

"Guide my research on cognitive load theory"
  → Socratic mode (deep-research)

"Review this paper" + paste your draft
  → Full review (EIC + 3 reviewers + Devil's Advocate)

"I received reviewer comments, here they are"
  → Mid-entry at Stage 4 (revision)

"Convert to LaTeX with IEEE format"
  → Format conversion mode

"Check my citations"
  → Citation compliance check
```

---

## Showcase

Real artifacts from a 10-stage pipeline run:

| Artifact | What it shows |
|:---------|:-------------|
| [Final Paper (EN)](examples/showcase/full_paper_apa7.pdf) | APA 7.0 formatted, LaTeX-compiled |
| [Final Paper (ZH)](examples/showcase/full_paper_zh_apa7.pdf) | Chinese version, APA 7.0 |
| [Integrity Report — Pre-Review](examples/showcase/integrity_report_stage2.5.pdf) | Caught 15 fabricated refs + 3 statistical errors |
| [Integrity Report — Final](examples/showcase/integrity_report_stage4.5.pdf) | Zero regressions confirmed |
| [Peer Review Round 1](examples/showcase/stage3_review_report.pdf) | EIC + 3 Reviewers + Devil's Advocate |
| [Response to Reviewers](examples/showcase/response_to_reviewers_r2.pdf) | Point-by-point author response |

**[Browse all artifacts →](examples/showcase/)**

---

## Supported Formats

| Category | Options |
|:---------|:--------|
| **Citation styles** | APA 7.0 (default), Chicago, MLA, IEEE, Vancouver |
| **Paper types** | IMRaD, Literature Review, Theoretical Analysis, Case Study, Policy Brief, Conference Paper |
| **Output formats** | Markdown, LaTeX, DOCX (Pandoc), PDF (tectonic) |
| **Languages** | English, Traditional Chinese (繁體中文), bilingual abstracts; intent detection works in any language |

---

## Architecture

```
Research → Write → Review → Revise → Publish
   |         |        |        |        |
Stage 1    Stage 2  Stage 3  Stage 4  Stage 5
   |         |        |        |        |
   +-- 2.5 --+        +-- 4.5 -+        +-- Stage 6
   Integrity           Integrity         Process Summary
   Gate                Gate              & Evaluation
```

- **Stage 2.5 & 4.5** — mandatory integrity gates (7-mode blocking checklist)
- **Material Passport** — tracks every artifact, every handoff
- **User confirmation** — required at every stage transition

**Full architecture:** [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md)

---

## Performance & Cost

| Pipeline | Est. Cost | Tokens |
|:---------|:----------|:-------|
| Full paper (15k words) | ~$4–6 | ~500k tokens |
| Single review | ~$1–2 | ~150k tokens |
| Lit review only | ~$0.50–1 | ~80k tokens |

Details: [docs/PERFORMANCE.md](docs/PERFORMANCE.md)

---

## What Makes ARG Different

### Anti-Sycophancy Engine
The Devil's Advocate scores every rebuttal (1-5) before responding. Concession only at score >= 4. No consecutive concessions allowed. Concession rate tracked across checkpoints.

### Intent-Aware Socratic Dialogue
Classifies your intent (exploratory vs. goal-oriented) at start and every 3 turns. Exploratory mode disables auto-convergence, raises max rounds to 60, and never asks "want me to summarize?"

### Dialogue Health Monitor
Silent self-assessment every 5 turns across 3 dimensions: persistent agreement, conflict avoidance, premature convergence. Auto-injects challenging questions when patterns detected.

### Three-Layer Citation Protocol
Layer 1: format compliance. Layer 2: source existence verification. Layer 3: claim-faithfulness anchoring — does the cited source actually support the claim being made?

---

## License

This project is licensed under the [MIT License](LICENSE).

Free to use, modify, and distribute — including commercial use. See [CONTRIBUTORS.md](CONTRIBUTORS.md) for attribution.
