<div align="center">

# Academic Research Graphify (ARG)

**Your AI-powered academic research copilot**

[![Version](https://img.shields.io/badge/version-v4.0.0-blue)](#)
[![License: MIT](https://img.shields.io/badge/license-MIT-green)](https://opensource.org/licenses/MIT)
[![Agents](https://img.shields.io/badge/agents-38-purple)](#the-agent-team)
[![Skills](https://img.shields.io/badge/skills-4-orange)](#skills--modes)
[![Modes](https://img.shields.io/badge/modes-26-red)](#skills--modes)

[繁體中文](README.zh-TW.md) | [Español](README.es.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [Português](README.pt-BR.md) | [हिन्दी](README.hi.md) | [العربية](README.ar.md) | [Русский](README.ru.md)

---

**38 specialized AI agents** across **4 skills** and **26 modes** — from research idea to publication-ready paper.  
Works with **any AI coding agent**: Windsurf, Cursor, Claude Code, GitHub Copilot, Cline, Aider, Continue, and more.

[Quick Start](#quick-start) · [Slash Commands](#slash-commands) · [All Modes](#all-modes-reference) · [Agent Team](#the-agent-team) · [Setup Guide](UNIVERSAL_SETUP.md)

</div>

---

## Why ARG?

> **AI is your copilot, not the pilot.** ARG doesn't write your paper for you. It handles the grunt work — hunting down references, formatting citations, verifying data, checking logical consistency — so you can focus on what actually requires your brain: defining the question, choosing the method, interpreting the data, and writing the sentence after *"I argue that..."*

Fully autonomous AI research pipelines inherit structural failure modes: hallucinated results, methodology fabrication, frame-lock, citation hallucinations. **These are not bugs — they're architectural.**

ARG is built on one premise: **a human researcher + AI avoids these failure modes better than either alone.**

| Problem | ARG's Solution |
|---------|---------------|
| Citation hallucinations | Semantic Scholar API verification + integrity gates |
| Frame-lock | Devil's Advocate with concession threshold protocol |
| Sycophancy | Anti-sycophancy scoring (1–5 scale before any concession) |
| Premature convergence | Intent detection + dialogue health monitoring |
| Methodology fabrication | 7-mode blocking checklist at Stage 2.5 & 4.5 |
| Unverifiable claims | Three-layer citation protocol + claim-faithfulness anchoring |

---

## Quick Start

```bash
git clone https://github.com/Masqiller/ARG-RESEARCHER-V4.1.git ~/ARG-Researcher
```

Open the repo in your IDE. Config files are auto-discovered:

| Agent | Config file | How commands work |
|:------|:------------|:------------------|
| **Google Antigravity** | `.agents/rules/arg-instructions.md` + `.agents/workflows/arg-*.md` | Native `/arg-*` slash commands in Agent Manager |
| **Windsurf** | `.windsurf/workflows/arg-*.md` | Native `/arg-*` slash commands in chat |
| **Cursor** | `.cursor/rules/arg-instructions.mdc` | Type `/arg-*` in chat |
| **Claude Code** | `.claude/CLAUDE.md` + `commands/` | Native `/arg-*` commands |
| **GitHub Copilot** | `.github/copilot-instructions.md` | Type `/arg-*` in chat |
| **Cline / Roo Code** | `.clinerules` | Type `/arg-*` in chat |
| **Aider** | `.aider/conventions.md` | Type `/arg-*` in chat |
| **Continue** | `.continue/config.json` | Type `/arg-*` in chat |
| **Any other agent** | `.ai/instructions.md` | Type `/arg-*` in chat |

**Test it:** Type `/arg-plan` and describe any paper topic. ARG will start a Socratic dialogue to map out your chapter structure in minutes.

> *Optional dependencies:* Pandoc (DOCX export), tectonic (PDF/LaTeX). Markdown output works without either.  
> **Detailed setup:** [UNIVERSAL_SETUP.md](UNIVERSAL_SETUP.md)

---

## Slash Commands

All commands follow the pattern `/arg-<mode>`. You can use them explicitly or just describe what you need in plain language — ARG detects your intent automatically.

---

### `/arg-full`
**Full end-to-end pipeline: research → write → review → revise → finalize**

The complete 10-stage orchestrated workflow. Invokes all 4 skills in sequence.

```
/arg-full
```

**What happens:**
1. `intake_agent` runs a configuration interview (topic, paper type, citation format, output format, word count, diagram preferences)
2. `deep-research` skill runs literature search (4-layer: Boolean → Citation Chaining → Forward Tracking → Semantic)
3. `academic-paper` skill drafts the full paper section by section with inline citations
   - Phase 2D: `diagram_master_agent` scans outline and plans diagrams (parallel with argument building)
   - Phase 4: diagrams are generated as TikZ/Mermaid/PGFPlots code and embedded in the draft
   - Phase 5: citation compliance, bilingual abstract, and diagram validation run in parallel
4. Mandatory integrity gate at Stage 2.5 (7-mode blocking checklist)
5. `academic-paper-reviewer` runs 5-reviewer panel (EIC + 3 peer reviewers + Devil's Advocate)
6. `draft_writer_agent` revises based on review (max 2 rounds)
7. Mandatory integrity gate at Stage 4.5
8. `formatter_agent` converts to your chosen output format
9. Process Summary + AI Self-Reflection Report

**When to use:** When you want a complete research paper from scratch with no prior materials.  
**Cost estimate:** ~$4–6 | ~500k tokens | 2–4 hours of collaborative work  
**Oversight:** Very High — user confirms at every stage transition

---

### `/arg-plan`
**Socratic chapter-by-chapter planning**

A guided dialogue to map your paper structure before any writing begins.

```
/arg-plan
```

**What happens:**
1. `socratic_mentor_agent` asks clarifying questions about your topic, scope, audience, and argument
2. Chapter-by-chapter negotiation — you decide what goes where and why
3. INSIGHTs are collected throughout the dialogue
4. After chapter planning, `diagram_master_agent` scans the plan for diagram opportunities (Categories 1–13), scores them 1–5, and presents a Diagram Plan for your confirmation
5. Produces three artifacts: **Chapter Plan** + **INSIGHT Collection** + **Confirmed Diagram Plan**

**When to use:** When you have a paper idea but aren't sure how to structure it. Run this before `/arg-full` or `/arg-outline`.  
**Oversight:** Very High — fully user-led Socratic dialogue  
**Output:** Chapter Plan + INSIGHT collection + Diagram Plan

---

### `/arg-outline`
**Detailed outline + evidence map**

Generates a structured paper outline with section-by-section source assignments and word count allocations.

```
/arg-outline
```

**What happens:**
1. `structure_architect_agent` reads your topic/RQ and literature
2. Builds a full outline (sections, subsections, key arguments per section)
3. Maps sources from the annotated bibliography to each section
4. Allocates word counts per section based on paper type
5. Produces an Evidence Map showing which source supports which claim

**When to use:** After you have your research question and sources, before writing the draft.  
**Oversight:** High  
**Output:** Detailed outline + evidence map + word count allocation table

---

### `/arg-lit-review`
**Annotated bibliography in paper format**

Produces a full literature review section ready to drop into your paper.

```
/arg-lit-review
```

**What happens:**
1. `literature_strategist_agent` runs the 4-layer search strategy
   - Layer 1: Boolean search across discipline-appropriate databases
   - Layer 2: Citation chaining (backward — finds foundational works)
   - Layer 3: Forward tracking (finds recent work citing the foundational papers)
   - Layer 4: Semantic search (catches cross-disciplinary gaps)
2. Screens sources against inclusion/exclusion criteria
3. Produces annotated bibliography (annotation per source: findings, relevance, quality, potential use)
4. Builds a Source × Theme literature matrix
5. Identifies 2–5 research gaps

> **Robotics/AI papers:** Automatically applies the Tier 1 venue registry (T-RO, RA-L, IJRR, Science Robotics, Nature MI, ICRA, IROS, CoRL, RSS…) with 2021–2026 time range priority. IEEE Access is supplementary only.

**When to use:** When you need a literature review section or an annotated bibliography.  
**Oversight:** Medium  
**Output:** Annotated bibliography + literature matrix + research gap analysis

---

### `/arg-abstract`
**Bilingual abstract (EN + zh-TW) + keywords**

Generates a publication-ready abstract in both English and Traditional Chinese.

```
/arg-abstract
```

**What you need to provide:** Your completed or near-complete paper draft (or at minimum a detailed outline + key findings).

**What happens:**
1. `abstract_bilingual_agent` reads the full paper
2. Produces a structured abstract covering: Background → Gap → Objective → Method → Results → Conclusion → Implications
3. Writes both EN and zh-TW versions following APA 7.0 abstract conventions
4. Generates 5–8 keywords in both languages

**When to use:** After your draft is complete, or when you only need an abstract for a submission.  
**Oversight:** Medium  
**Output:** EN abstract + zh-TW abstract + bilingual keyword list

---

### `/arg-revision`
**Revised draft + point-by-point R&R responses**

Takes reviewer comments and produces a revised manuscript with a formal response letter.

```
/arg-revision
```

**What you need to provide:** Your original draft + reviewer comments (paste directly or attach).

**What happens:**
1. `revision_coach_agent` categorizes every reviewer comment by severity (Critical / Major / Minor / Suggestion)
2. Builds a Revision Roadmap — maps each comment to a specific action and section
3. `draft_writer_agent` executes all Critical and Major revisions, attempts Minor revisions within word count
4. Logs every change in a Revision Log (item → section → action taken → status)
5. Produces a formal Response to Reviewers letter with point-by-point responses

**When to use:** After receiving peer review comments (R&R or major/minor revision decision).  
**Oversight:** High  
**Output:** Revised draft + Revision Log + Response to Reviewers letter

---

### `/arg-revision-coach`
**Revision roadmap + response letter skeleton**

Parses reviewer comments and gives you a structured roadmap — without rewriting the paper for you.

```
/arg-revision-coach
```

**What you need to provide:** Your reviewer comments.

**What happens:**
1. `revision_coach_agent` reads and categorizes every comment
2. Identifies the underlying issue behind each comment (not just the surface request)
3. Produces a Revision Roadmap: what to fix, where, and how
4. Produces a Response Letter Skeleton with suggested tone and framing for each point
5. Does **not** rewrite the paper — you do the writing, guided by the roadmap

**When to use:** When you want to handle the revision yourself but need structured guidance.  
**Oversight:** Medium  
**Output:** Revision Roadmap + Response Letter Skeleton

---

### `/arg-citation-check`
**Citation error report + auto-corrections**

Audits every citation in your paper for format compliance and cross-references.

```
/arg-citation-check
```

**What you need to provide:** Your paper draft with in-text citations and a reference list.

**What happens:**
1. `citation_compliance_agent` builds a Citation Index from all in-text citations and the reference list
2. **Zero-orphan check** — every in-text citation must appear in the reference list and vice versa
3. **Format compliance** — checks every APA/IEEE/Chicago/MLA/Vancouver rule for your selected style
4. **DOI check** — verifies DOI format (`https://doi.org/...`), flags missing DOIs
5. **Auto-corrects** deterministic errors directly (wrong `&` vs `and`, wrong ordering, wrong DOI format, etc.)
6. **Flags** ambiguous cases for human review (e.g., claim may not match the cited source)
7. Self-citation ratio check (flags if > 15%)
8. Source currency check (flags sources older than 10 years unless seminal)

**When to use:** Before submitting any paper, or after receiving "citation errors" from a reviewer.  
**Oversight:** Low (mechanical)  
**Output:** Citation Audit Report + corrected reference list

---

### `/arg-format-convert`
**Convert your paper to LaTeX, DOCX, PDF, or Markdown**

Converts your draft to the target output format with full citation and style compliance.

```
/arg-format-convert
```

**What you need to provide:** Your paper draft + target format + target journal/style (optional).

**What happens:**
1. `formatter_agent` reads your draft and the Paper Configuration Record
2. For **LaTeX**: generates `.tex` + `.bib`, injects correct preamble packages, applies journal template if specified
3. For **DOCX**: runs Pandoc conversion with APA/journal style template applied
4. For **PDF**: compiles via tectonic (LaTeX → PDF)
5. For **Markdown**: cleans and structures the draft as clean `.md`
6. Citation format is converted to match the target (e.g., author-date → numbered IEEE)

**When to use:** When you need to submit to a specific venue requiring a specific format, or to switch formats.  
**Oversight:** Low  
**Output:** Formatted document in target format

---

### `/arg-disclosure`
**Venue-specific AI-usage disclosure statement**

Generates a compliant AI usage statement tailored to your target journal or conference.

```
/arg-disclosure
```

**What you need to provide:** Target venue name (journal or conference).

**What happens:**
1. Agent reads the venue's AI disclosure policy
2. Generates a disclosure statement matching the venue's required format and scope
3. Specifies exactly which parts of the workflow used AI assistance
4. Formatted for direct insertion into the manuscript

**When to use:** Before submission to any venue that requires an AI usage declaration.  
**Oversight:** Low  
**Output:** Venue-formatted AI disclosure statement

---

### `/arg-diagram`
**Standalone structural diagram generation (TikZ / Mermaid / PGFPlots)**

Generates publication-quality structural and conceptual diagrams on demand.

```
/arg-diagram
```

**What you need to provide:** A description of what you want to visualize (e.g., "a methodology flowchart for my 3-stage pipeline", "a system architecture diagram", "a comparison matrix of 4 methods").

**What happens:**
1. `diagram_master_agent` (Dr. Atlas) classifies your request into one of 13 diagram categories:
   - Methodology flowchart, System/software architecture, Neural/ML architecture, Conceptual framework, Experimental pipeline, Taxonomy/hierarchy tree, Comparison/ablation matrix, Algorithm pseudocode flow, Commutative/categorical diagram, Timeline/Gantt, State machine, Data flow, Mathematical function plot
2. Selects the appropriate engine: **TikZ** (default for all), **PGFPlots** (function plots), **Mermaid** (Markdown-only output)
3. Generates complete, compilable code with `\caption{}`, `\label{}`, preamble requirements, and in-text reference
4. Runs validator self-check (syntax, package validity, label cross-references)
5. Presents output with up to 2 refinement rounds

**When to use:** When you need a specific diagram for your paper without running the full pipeline.  
**Oversight:** Medium  
**Output:** TikZ/PGFPlots LaTeX code or Mermaid Markdown code, ready to paste into your paper

---

## All Modes Reference

### `deep-research` — 7 modes

| Mode | Slash Command | What you say | Output | Cost |
|------|--------------|--------------|--------|------|
| `full` | — | "research [topic]", "deep research on..." | APA 7.0 report, 3–8k words | ~$1–2 |
| `quick` | — | "quick brief on...", "30-minute summary" | Research brief, 500–1,500 words | ~$0.20 |
| `review` | — | "review this paper", "evaluate this source" | Reviewer report on provided text | ~$0.50 |
| `lit-review` | `/arg-lit-review` | "literature review", "annotated bibliography" | Annotated bib + synthesis | ~$0.50–1 |
| `fact-check` | — | "verify claims", "fact-check this" | Claim-by-claim verification report | ~$0.30 |
| `socratic` | — | "guide my research", "help me think through" | Research Plan + INSIGHT collection | ~$0.50 |
| `systematic-review` | — | "systematic review", "meta-analysis", "PRISMA" | PRISMA 2020 report, 5–15k words | ~$2–3 |

### `academic-paper` — 11 modes

| Mode | Slash Command | What you say | Output | Cost |
|------|--------------|--------------|--------|------|
| `full` | — | "write a paper on...", "academic paper about..." | Complete paper draft | ~$3–4 |
| `plan` | `/arg-plan` | "guide my paper", "help me plan chapter by chapter" | Chapter Plan + Diagram Plan + INSIGHTs | ~$0.50 |
| `outline-only` | `/arg-outline` | "paper outline", "just need an outline" | Detailed outline + evidence map | ~$0.30 |
| `revision` | `/arg-revision` | "revise paper", "incorporate reviewer feedback" | Revised draft + R&R responses | ~$1–2 |
| `revision-coach` | `/arg-revision-coach` | "parse reviews", "I got reviewer comments" | Revision Roadmap + Response Letter Skeleton | ~$0.30 |
| `abstract-only` | `/arg-abstract` | "write abstract", "generate abstract" | Bilingual abstract (zh-TW + EN) + keywords | ~$0.20 |
| `lit-review` | `/arg-lit-review` | "literature review paper", "write a lit review" | Annotated bibliography in paper format | ~$0.50 |
| `format-convert` | `/arg-format-convert` | "convert to LaTeX", "export as DOCX" | Formatted document | ~$0.20 |
| `citation-check` | `/arg-citation-check` | "check citations", "verify references" | Citation Audit Report + corrected refs | ~$0.20 |
| `disclosure` | `/arg-disclosure` | "AI disclosure for [venue]" | Venue-specific AI usage statement | ~$0.10 |
| `diagram` | `/arg-diagram` | "generate diagram", "draw a flowchart for my paper" | TikZ/Mermaid/PGFPlots diagram code | ~$0.20 |

### `academic-paper-reviewer` — 6 modes

| Mode | Slash Command | What you say | Output | Cost |
|------|--------------|--------------|--------|------|
| `full` | — | "review paper", "peer review", "manuscript review" | 5 review reports + Editorial Decision + Revision Roadmap | ~$1–2 |
| `re-review` | — | "check revisions", "verification review" | Revision verification checklist + residual issues | ~$0.50 |
| `quick` | — | "quick review", "quick look" | EIC quick assessment + key issues | ~$0.30 |
| `methodology-focus` | — | "check methodology", "focus on methods" | In-depth methodology review | ~$0.50 |
| `guided` | — | "guide me to improve", "walk me through issues" | Socratic issue-by-issue dialogue | ~$0.50 |
| `calibration` | — | "calibrate reviewer", "measure reviewer accuracy" | Calibration Report (FNR/FPR/AUC) | ~$0.30 |

### `academic-pipeline` — orchestrator

| Mode | What you say | Output |
|------|--------------|--------|
| Full pipeline | "full paper workflow", "research to paper end-to-end" | 10-stage orchestrated workflow: research → write → integrity gate → review → revise → integrity gate → finalize |
| Resume | "resume from passport", "continue pipeline from reset boundary" | Resumes a prior pipeline run from a saved Material Passport checkpoint |

---

## The Agent Team

ARG deploys **38 specialized agents**, each with a named persona and a defined role:

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
<summary><strong>Academic Paper Agents (13)</strong></summary>

| Agent | Persona | Role |
|:------|:--------|:-----|
| Intake Agent | Dr. Smit | Paper configuration interview (topic, format, citations, diagram preferences) |
| Literature Strategist | Dr. Mridankan | 4-layer search strategy & source selection with discipline-specific venue registries |
| Structure Architect | Dr. Aditya | Paper structure design, outline, evidence mapping |
| Argument Builder | Dr. Arvind | Logical CER chain construction per section |
| Draft Writer | Dr. Kavya | Academic prose drafting (TEEL paragraphs, three-layer citation emission) |
| Citation Compliance | Dr. Rohan | Citation format verification, auto-correction, zero-orphan enforcement |
| Abstract Bilingual | Dr. Priya | Bilingual abstract composition (EN + zh-TW) |
| Peer Reviewer | Dr. Vikram | Simulated peer review with severity scoring |
| Formatter | Dr. Neha | Output format conversion (LaTeX / DOCX / PDF / Markdown) |
| Socratic Mentor | Dr. Arjun | Chapter-by-chapter Socratic planning dialogue |
| Visualization | Dr. Meera | Publication-quality figure specs (matplotlib / seaborn / ggplot2) |
| Revision Coach | Dr. Ishaan | Reviewer comment parsing, Revision Roadmap, R&R response skeleton |
| **Diagram Master** | **Dr. Atlas** | **Structural diagram generation: TikZ / PGFPlots / PlotNeuralNet / Mermaid — 13 diagram categories, 3 sub-roles (Planner / Generator / Validator)** |

</details>

<details>
<summary><strong>Paper Reviewer Agents (7)</strong></summary>

| Agent | Persona | Role |
|:------|:--------|:-----|
| Field Analyst | Dr. Tanvi | Paper field identification & reviewer team configuration |
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

## Recommended Workflow

For the highest quality output, run these four steps in sequence. Each step feeds into the next.

```
Step 1 — Deep Research
  /deep-research
  "Research [your topic]" or "Guide my research on [topic]"
  → Produces: Annotated Bibliography, Synthesis Report, RQ Brief

         ↓  hand off literature + RQ to next step

Step 2 — Paper Planning
  /arg-plan
  "Help me plan my paper on [topic]" (paste your RQ and key findings from Step 1)
  → Produces: Chapter Plan, INSIGHT Collection, Diagram Plan

         ↓  hand off Chapter Plan to next step

Step 3 — Plan Review
  /academic-paper-reviewer  (use quick or guided mode on the Chapter Plan)
  "Quick review of this chapter plan" (paste the Chapter Plan from Step 2)
  → Produces: Structural feedback, gap analysis, argument stress-test

         ↓  incorporate feedback, then run the full pipeline

Step 4 — Full Pipeline
  /arg-full
  "Write a complete paper on [topic]" (paste your approved Chapter Plan + literature from Steps 1–2)
  → Produces: Complete paper draft → integrity gate → peer review → revision → final output
```

### Why this order?

| Step | Why it matters |
|------|---------------|
| **Deep Research first** | ARG writes from a verified bibliography. Running research before planning ensures every argument has a source already identified. |
| **Plan before writing** | `/arg-plan` uses Socratic dialogue — you make structural decisions before any prose is generated. Changes at this stage cost seconds, not hours. |
| **Review the plan** | The `academic-paper-reviewer` catches logical gaps and weak arguments in the Chapter Plan before the draft exists. Far cheaper to fix structure now than after 10,000 words are written. |
| **Full pipeline last** | `/arg-full` already includes research, planning, review, and revision internally — but when you feed it a pre-approved Chapter Plan and bibliography from Steps 1–3, it skips the early uncertainty phases and produces a tighter draft in fewer iterations. |

> **Shortcut:** If you're in a hurry, just run `/arg-full` directly. It runs all 10 stages internally. The 4-step workflow above gives you more control and typically better structure at the cost of more upfront dialogue.

---

## Which Command Should I Use?

| I want to... | Use this |
|-------------|----------|
| Explore a vague idea before committing to a topic | Describe it in plain language — triggers `socratic` mode |
| Map out my paper chapter by chapter | `/arg-plan` |
| Get a full outline with source assignments | `/arg-outline` |
| Do a literature review only | `/arg-lit-review` |
| Write a full paper from scratch | `/arg-full` or say "write a paper about..." |
| Run the complete research + write + review pipeline | `/arg-full` |
| Get my draft peer-reviewed | Say "review this paper" + paste draft |
| Incorporate reviewer comments | `/arg-revision` |
| Parse reviewer comments, write the response myself | `/arg-revision-coach` |
| Write just the abstract | `/arg-abstract` |
| Generate a diagram for my paper | `/arg-diagram` |
| Check and fix my citations | `/arg-citation-check` |
| Convert my draft to LaTeX / DOCX / PDF | `/arg-format-convert` |
| Generate an AI usage disclosure for a journal | `/arg-disclosure` |

---

## Architecture

### Full Pipeline (`/arg-full`)

```
Stage 1  — Deep Research
           Literature search (4-layer) → Annotated Bibliography → Synthesis Report

Stage 2  — Academic Paper Drafting
           Phase 1: intake + configuration interview
           Phase 2: structure_architect → outline + evidence map
           Phase 2D: diagram_master_agent → Diagram Plan  ─┐ (parallel)
           Phase 3: argument_builder → CER chains          ─┘
           Phase 4: draft_writer → full paper draft
                    + diagram_master_agent → TikZ/Mermaid code embedded
           Phase 5a: citation_compliance_agent (parallel)
           Phase 5b: abstract_bilingual_agent  (parallel)
           Phase 5c: diagram_master_agent Validator (parallel)

Stage 2.5 — Integrity Gate (mandatory, 7-mode blocking checklist)

Stage 3  — Peer Review
           field_analyst → eic_agent → 3 reviewers + devil's advocate → editorial synthesis

Stage 4  — Revision
           revision_coach → draft_writer (max 2 rounds)

Stage 4.5 — Final Integrity Gate (mandatory)

Stage 5  — Re-Review (max 2 loops)

Stage 6  — Format Conversion + Finalization
           formatter_agent → LaTeX / DOCX / PDF / Markdown

           Process Summary + AI Self-Reflection Report
```

- **Stage 2.5 & 4.5** — mandatory integrity gates (cannot be skipped)
- **Material Passport** — every artifact, every handoff, every claim tracked
- **User confirmation** — required at every stage transition

---

## Supported Formats

| Category | Options |
|:---------|:--------|
| **Citation styles** | APA 7.0 (default), Chicago 17th, MLA 9th, IEEE, Vancouver |
| **Paper types** | IMRaD, Literature Review, Theoretical Analysis, Case Study, Policy Brief, Conference Paper |
| **Output formats** | Markdown, LaTeX (.tex + .bib), DOCX (via Pandoc), PDF (via tectonic) |
| **Diagram engines** | TikZ (all categories), PGFPlots (function plots), PlotNeuralNet (neural architectures), Mermaid (Markdown-only) |
| **Languages** | English, Traditional Chinese (繁體中文), bilingual abstracts |

---

## Performance & Cost

| Workflow | Est. Cost | Tokens | Time |
|:---------|:----------|:-------|:-----|
| Full pipeline — 15k word paper | ~$4–6 | ~500k | 2–4 hrs collaborative |
| Academic paper only (no research) | ~$3–4 | ~350k | 1–2 hrs |
| Single peer review | ~$1–2 | ~150k | 20–40 min |
| Literature review only | ~$0.50–1 | ~80k | 15–30 min |
| Diagram generation (standalone) | ~$0.20 | ~20k | 5 min |
| Citation check | ~$0.20 | ~15k | 5 min |

---

## What Makes ARG Different

### Anti-Sycophancy Engine
The Devil's Advocate scores every rebuttal (1–5) before responding. Concession only at score ≥ 4. No consecutive concessions allowed. Concession rate tracked across all checkpoints.

### Intent-Aware Socratic Dialogue
Classifies your intent (exploratory vs. goal-oriented) at start and every 3 turns. Exploratory mode disables auto-convergence, raises max rounds to 60, and never asks "want me to summarize?"

### Dialogue Health Monitor
Silent self-assessment every 5 turns across 3 dimensions: persistent agreement, conflict avoidance, premature convergence. Auto-injects challenging questions when patterns detected.

### Three-Layer Citation Protocol
- **Layer 1** — format compliance (APA/IEEE/Chicago/MLA/Vancouver rules)
- **Layer 2** — source existence verification (DOI, retraction check)
- **Layer 3** — claim-faithfulness anchoring — does the cited source actually support the claim being made? (`<!--anchor:page:14-->` markers, verified by `cite_provenance_finalizer_agent`)

### Diagram Master Agent (v4.0)
`diagram_master_agent` (Dr. Atlas) generates structural diagrams as compilable TikZ/PGFPlots/Mermaid code — not descriptions or placeholders. Runs in three phases: Planner (identifies and scores opportunities), Generator (produces code), Validator (syntax + cross-reference checks). Integrated into both `/arg-plan` and `/arg-full`.

### Discipline-Aware Literature Search
`literature_strategist_agent` applies discipline-specific venue registries. For Robotics/AI: Tier 1 venues (T-RO, RA-L, IJRR, Science Robotics, Nature MI, ICRA, IROS, CoRL, RSS) are searched first, 2021–2026 time range enforced, IEEE Access restricted to supplementary use only.

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

## License

This project is licensed under the [MIT License](LICENSE).

Free to use, modify, and distribute — including commercial use.
