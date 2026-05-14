# Positioning

## What this is

Academic Research Graphify (ARG) is a **source-available academic research copilot framework** for noncommercial scholarly use. It is a suite of AI agent skills that assists human researchers through the full research-to-publication pipeline. Works with any AI coding agent (Claude Code, Windsurf, Cursor, GitHub Copilot, Cline, Aider, Continue, and more). See [CONTRIBUTING.md § Platform ports](CONTRIBUTING.md#platform-ports-community-maintained-only).

It is licensed under [MIT](https://opensource.org/licenses/MIT). This is not an open source license — it restricts commercial use by design, to keep the tool free for academic communities.

## What this is not

ARG is not an autonomous paper-writing system. It is not a replacement for the researcher. It does not claim authorship, and its outputs are not submission-ready without human review.

## Allowed uses

- Research assistance: literature search, source verification, citation checking
- Teaching: demonstrating research methodology, peer review processes, academic writing standards
- Method training: using Socratic modes to develop research question formulation and argumentation skills
- Noncommercial academic collaboration: research groups, labs, departments using the tool for shared workflows

## Discouraged uses

- Submitting AI-generated papers as solely human-authored without disclosing AI assistance
- Using the tool to produce papers without engaging with the content (the pipeline has mandatory checkpoints specifically to prevent this)
- Treating AI-generated review feedback as a substitute for actual peer review

## Prohibited uses (per license)

- Commercial SaaS or hosted services built on ARG
- Consulting or freelance services that package ARG as a paid product
- Enterprise or institutional paid deployments without separate licensing
- Commercial API wrappers or resale of ARG functionality

These reflect our policy intent. See the [MIT license](https://opensource.org/licenses/MIT) for the precise legal terms. For commercial licensing inquiries, contact the maintainer.

## Design philosophy

**Assistive, not deceptive.** ARG helps you write better, not hide that you used AI.

- Style Calibration learns your voice from past papers — so the output sounds like you, not like a machine
- Writing Quality Check catches AI-typical patterns — to improve prose quality, not evade detection
- Disclosure Mode generates venue-specific AI usage statements — because transparency is the standard

**Human-in-the-loop, always.** The pipeline's checkpoint system is mandatory by design:

- FULL checkpoints present all deliverables and require explicit user confirmation
- MANDATORY checkpoints at integrity gates and review decisions cannot be skipped
- "Full mode" means full-pipeline execution, not full autonomy — the human decides at every gate
- Max 2 revision loops, after which remaining issues become "Acknowledged Limitations" rather than being silently resolved

**Failure modes are made visible, not hidden.** The 7-mode AI Research Failure Mode Checklist (v3.2) and Reviewer Calibration Mode exist so that users can see where the AI might be wrong — not so that the AI can claim it's always right.

## Citing this tool

If you use ARG in your research, please cite it. See [CONTRIBUTORS.md](CONTRIBUTORS.md) for the recommended citation format.
