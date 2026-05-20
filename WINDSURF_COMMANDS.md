# Windsurf Slash Commands — Complete Reference

All **26 workflow commands** across the 4 ARG skills, available as native `/slash-commands` in Windsurf via `.windsurf/workflows/`.

> **How to use:** Type the command in the Windsurf chat panel, optionally followed by a file path, topic, or paper text.  
> **Auto-detection:** You can also describe what you need in plain language — ARG detects intent and routes to the right mode automatically.

---

## Quick Picker

| I want to… | Command |
|------------|---------|
| Full pipeline — research → write → review → revise → finalize | `/arg-full` |
| Write a paper (standalone, no pipeline) | `/arg-paper` |
| Plan my paper chapter by chapter | `/arg-plan` |
| Generate a detailed outline | `/arg-outline` |
| Do a literature review or annotated bibliography | `/arg-lit-review` |
| Write just the abstract | `/arg-abstract` |
| Revise my paper with reviewer comments | `/arg-revision` |
| Parse reviews and get a roadmap (I'll write) | `/arg-revision-coach` |
| Check and fix my citations | `/arg-citation-check` |
| Convert to LaTeX / DOCX / PDF | `/arg-format-convert` |
| Generate AI disclosure for a journal | `/arg-disclosure` |
| Generate a standalone diagram (TikZ/Mermaid) | `/arg-diagram` |
| Deep research on any topic (full APA report) | `/arg-deep-research` |
| Quick research brief (500–1,500 words) | `/arg-deep-research-quick` |
| Evaluate a paper or source against research standards | `/arg-deep-research-review` |
| Annotated bibliography + thematic synthesis | `/arg-deep-research-lit-review` |
| Fact-check claims in a paper | `/arg-deep-research-fact-check` |
| Guide my research direction (I'm not sure what to study) | `/arg-deep-research-socratic` |
| Full systematic review — PRISMA 2020 | `/arg-deep-research-systematic-review` |
| Peer review a paper (5 reviewers + Editorial Decision) | `/academic-paper-reviewer` |
| Verify that revisions addressed review comments | `/arg-reviewer-re-review` |
| Quick 15-minute EIC assessment | `/arg-reviewer-quick` |
| In-depth methodology review only | `/arg-reviewer-methodology` |
| Guided review — understand issues through dialogue | `/arg-reviewer-guided` |
| Calibrate reviewer accuracy (FNR/FPR/AUC) | `/arg-reviewer-calibration` |
| Resume a pipeline from a saved checkpoint | `/arg-pipeline-resume` |

---

## Skill 1 — `academic-pipeline` (2 commands)

### `/arg-full`
**Full end-to-end pipeline: research → write → review → revise → finalize**

Orchestrates all 4 skills in a 10-stage workflow. Starts from scratch — runs deep research first, then writes the paper, passes through two integrity gates, runs peer review, revises, and finalises.

- **When to use:** When you want a complete research paper from scratch with no prior materials.
- **Oversight:** Very High — user confirms at every stage transition
- **Cost:** ~$4–6 | ~500k tokens | 2–4 hours
- **Output:** Complete paper draft → integrity report → 5-reviewer review → revised draft → final formatted paper + Process Summary

---

### `/arg-pipeline-resume`
**Resume a prior pipeline run from a saved Material Passport checkpoint**

Resumes a cross-session pipeline run using `resume_from_passport=<hash>`. Requires the original session to have run with `ARS_PASSPORT_RESET=1`.

- **When to use:** When a long pipeline run was interrupted and you want to continue in a fresh session without losing progress.
- **Oversight:** High — pending decisions are always surfaced first
- **Usage:** `/arg-pipeline-resume` then provide `resume_from_passport=<hash>`
- **Output:** Pipeline resumes at the recorded stage with all prior materials loaded

---

## Skill 2 — `academic-paper` (11 commands)

### `/arg-paper`
**Write a complete paper draft (standalone — no pipeline)**

Runs the 12-agent `academic-paper` skill directly. Use this when you already have research materials or want to write a paper without the full deep-research pipeline.

- **When to use:** You have a topic or notes and want a complete paper draft now.
- **Oversight:** High — configuration interview at start
- **Cost:** ~$3–4 | ~350k tokens | 1–2 hours
- **Output:** Complete paper draft (LaTeX/DOCX/PDF/Markdown) + bilingual abstract + citation-checked references

---

### `/arg-plan`
**Socratic chapter-by-chapter planning**

Guides you through paper structure decisions via Socratic dialogue before any writing begins. Ends with a Diagram Plan.

- **When to use:** You have a paper idea but aren't sure how to structure it. Run before `/arg-paper` or `/arg-full`.
- **Oversight:** Very High — fully user-led
- **Cost:** ~$0.50
- **Output:** Chapter Plan + INSIGHT collection + Diagram Plan

---

### `/arg-outline`
**Detailed outline + evidence map**

Generates a structured paper outline with source assignments and word count allocations per section.

- **When to use:** After you have your research question and sources, before drafting.
- **Oversight:** High
- **Cost:** ~$0.30
- **Output:** Detailed outline + evidence map + word count allocation table

---

### `/arg-lit-review`
**Annotated bibliography in paper format**

Runs a 4-layer literature search and builds an annotated bibliography ready to drop into your paper.

- **When to use:** When you need a literature review section or standalone annotated bibliography.
- **Oversight:** Medium
- **Cost:** ~$0.50–1
- **Output:** Annotated bibliography + literature matrix + research gap analysis

---

### `/arg-abstract`
**Bilingual abstract (EN + zh-TW) + keywords**

Generates a structured abstract in both English and Traditional Chinese from your completed draft.

- **When to use:** After your draft is complete, or when submitting to a bilingual venue.
- **Oversight:** Medium
- **Cost:** ~$0.20
- **Output:** EN abstract + zh-TW abstract + bilingual keyword list (5–8 keywords)

---

### `/arg-revision`
**Revised draft + point-by-point R&R responses**

Takes your reviewer comments and produces a revised manuscript with a formal response letter.

- **When to use:** After receiving peer review comments (R&R or major/minor revision).
- **Oversight:** High
- **Cost:** ~$1–2
- **Output:** Revised draft + Revision Log + Response to Reviewers letter

---

### `/arg-revision-coach`
**Revision roadmap + response letter skeleton (you write)**

Parses reviewer comments into a structured roadmap without rewriting the paper for you.

- **When to use:** When you want to handle the revision yourself but need structured guidance.
- **Oversight:** Medium
- **Cost:** ~$0.30
- **Output:** Revision Roadmap + Response Letter Skeleton

---

### `/arg-citation-check`
**Citation audit report + auto-corrections**

Audits every citation for format compliance, zero-orphan enforcement, DOI validity, and self-citation ratio.

- **When to use:** Before submitting any paper, or after receiving citation errors from a reviewer.
- **Oversight:** Low (mechanical)
- **Cost:** ~$0.20
- **Output:** Citation Audit Report + corrected reference list

---

### `/arg-format-convert`
**Convert to LaTeX / DOCX / PDF / Markdown**

Converts your draft to any target output format with full citation and style compliance.

- **When to use:** When submitting to a venue requiring a specific format, or switching formats.
- **Oversight:** Low
- **Cost:** ~$0.20
- **Output:** Formatted document in target format (.tex + .bib / .docx / .pdf / .md)

---

### `/arg-disclosure`
**Venue-specific AI-usage disclosure statement**

Generates a compliant AI usage statement tailored to your target journal or conference's policy.

- **When to use:** Before submission to any venue that requires an AI usage declaration.
- **Oversight:** Low
- **Cost:** ~$0.10
- **Output:** Venue-formatted AI disclosure statement, ready to insert into the manuscript

---

### `/arg-diagram`
**Standalone diagram (TikZ / Mermaid / PGFPlots)**

Generates a publication-quality structural or conceptual diagram from a plain-language description.

- **When to use:** When you need a specific diagram without running the full pipeline.
- **Oversight:** Medium
- **Cost:** ~$0.20
- **Output:** Compilable TikZ / PGFPlots LaTeX code or Mermaid Markdown code + caption + preamble requirements

---

## Skill 3 — `deep-research` (7 commands)

### `/arg-deep-research`
**Full APA 7.0 research report (3,000–8,000 words)**

Runs the 13-agent deep-research pipeline: scope → literature search → source verification → synthesis → APA 7.0 report → editorial + ethics review → final polish.

- **When to use:** When you need rigorous academic research on any topic.
- **Oversight:** High — RQ confirmed before research begins
- **Cost:** ~$1–2 | ~120k tokens
- **Output:** Full APA 7.0 research report with annotated bibliography, synthesis, gaps analysis, and AI disclosure

---

### `/arg-deep-research-quick`
**Research brief (500–1,500 words)**

Compressed research pipeline — top sources only, no full synthesis pass.

- **When to use:** Quick background check, 30-minute overview, or briefing notes.
- **Oversight:** Medium
- **Cost:** ~$0.20
- **Output:** Concise brief: Executive Summary + Key Findings + Evidence Summary + Gaps + References

---

### `/arg-deep-research-review`
**Reviewer report on a provided paper or text**

Evaluates a provided paper or passage against deep-research evidence quality standards.

- **When to use:** When you want to assess a paper's research quality (evidence hierarchy, literature coverage, synthesis rigour). For structured peer review, use `/academic-paper-reviewer` instead.
- **Oversight:** High
- **Cost:** ~$0.50
- **Output:** Reviewer Report with strengths, issues by severity, evidence gaps, and per-dimension scores

---

### `/arg-deep-research-lit-review`
**Annotated bibliography + thematic synthesis**

Systematic literature search across 15–30 sources, with annotations and thematic grouping.

- **When to use:** When you need a standalone literature review with thematic synthesis (not a paper section — use `/arg-lit-review` for that).
- **Oversight:** Medium
- **Cost:** ~$0.50–1
- **Output:** Annotated bibliography (APA 7.0) + thematic synthesis paragraphs + research gap list

---

### `/arg-deep-research-fact-check`
**Claim-by-claim verification report**

Verifies each claim in a provided text against primary sources and the evidence hierarchy.

- **When to use:** Before publishing or citing a passage, or when a reviewer questions specific claims.
- **Oversight:** Medium
- **Cost:** ~$0.30
- **Output:** Claim-by-claim table (Claim | Verdict | Confidence | Evidence | Correction) + accuracy summary

---

### `/arg-deep-research-socratic`
**Guided research direction dialogue + Research Plan Summary**

Helps you crystallise a vague research interest into a focused, researchable question through Socratic dialogue.

- **When to use:** When you're uncertain what to research or where to start. Auto-activates when intent is exploratory.
- **Oversight:** Very High — fully user-led
- **Cost:** ~$0.50
- **Output:** Research Plan Summary (confirmed RQ + methodology blueprint + search terms) + INSIGHT collection

---

### `/arg-deep-research-systematic-review`
**PRISMA 2020 systematic review (5,000–15,000 words) + optional meta-analysis**

Full systematic review following PRISMA 2020 protocol: PICO(S) definition → screening → inclusion → risk of bias → synthesis → report.

- **When to use:** For formal systematic reviews or meta-analyses.
- **Oversight:** Medium
- **Cost:** ~$2–3
- **Output:** Full PRISMA 2020 structured report + flow diagram (text) + extraction table + optional meta-analysis (effect sizes, I², forest plot description)

---

## Skill 4 — `academic-paper-reviewer` (6 commands)

### `/academic-paper-reviewer`
**Full peer review: 5 reviewers + Editorial Decision + Revision Roadmap**

Simulates a complete international journal peer review process with 5 independent reviewers: Editor-in-Chief, Methodology Reviewer, Domain Expert, Perspective Reviewer, and Devil's Advocate.

- **When to use:** Pre-submission review, or when you want thorough structured feedback on a complete draft.
- **Oversight:** High — reviewer configuration confirmed at Phase 0
- **Cost:** ~$1–2 | ~150k tokens | 20–40 min
- **Output:** 5 independent review reports + cross-reviewer consensus matrix + Editorial Decision Letter + Revision Roadmap
- **Iron Rule:** If the Devil's Advocate finds CRITICAL issues → Decision cannot be Accept

---

### `/arg-reviewer-re-review`
**Revision verification: did the revision actually address the comments?**

Verifies whether each revision roadmap item was addressed in the revised manuscript. Uses an R&R Traceability Matrix.

- **When to use:** After revising a paper to check whether all review comments are properly addressed before re-submission.
- **Oversight:** Medium
- **Cost:** ~$0.50
- **Input required:** Original Revision Roadmap + revised manuscript (+ optional Author Response letter)
- **Output:** Traceability matrix (Roadmap item | Author's Claim | Verified?) + residual issues + new issues + new Decision

---

### `/arg-reviewer-quick`
**15-minute EIC quick assessment**

Rapid top-level quality check by the Editor-in-Chief only.

- **When to use:** Quick sanity check before investing in a full review, or to decide if a draft is ready for submission.
- **Oversight:** Low
- **Cost:** ~$0.30
- **Output:** EIC Quick Assessment (≤500 words) + top 3 blocking issues + preliminary recommendation

---

### `/arg-reviewer-methodology`
**In-depth methodology review (2-reviewer panel)**

Deep dive into research design, statistical validity, and reproducibility. Runs EIC + Methodology Reviewer (Sprint Contract v3.6.2).

- **When to use:** When you specifically need methodology feedback — experimental design, stats, sampling, reproducibility.
- **Oversight:** Medium
- **Cost:** ~$0.50
- **Output:** Scored methodology rubric + ordered issue list (Critical → Minor) + specific improvement suggestions

---

### `/arg-reviewer-guided`
**Guided review — understand issues through Socratic dialogue**

All 5 reviewers run internally, but issues are revealed to you one at a time through questions rather than a report dump.

- **When to use:** When you want to understand and own the problems yourself rather than receive a list. Especially useful for learning or for junior researchers.
- **Oversight:** Very High — fully user-led
- **Cost:** ~$0.50
- **Output:** Your self-formulated revision strategy + reprioritised Revision Roadmap based on dialogue

---

### `/arg-reviewer-calibration`
**Reviewer calibration report (FNR / FPR / AUC)**

Measures this reviewer's False Negative Rate, False Positive Rate, and balanced accuracy against a user-supplied gold set. Opt-in — run once per domain before relying on rubric scores.

- **When to use:** Before using the reviewer's scores for high-stakes decisions (e.g., selecting between papers, grading).
- **Oversight:** Medium
- **Cost:** ~$0.30 per gold paper × N papers
- **Input required:** 5–20 papers with known outcomes (Accept / Reject / Revision + final decision)
- **Output:** Calibration Report (FNR/FPR/balanced accuracy/AUC) + per-dimension calibration error + session-scoped confidence disclosure

---

## Summary Table — All 26 Commands

| Command | Skill | Mode | Oversight | Est. Cost |
|---------|-------|------|:---------:|:---------:|
| `/arg-full` | academic-pipeline | pipeline | Very High | ~$4–6 |
| `/arg-pipeline-resume` | academic-pipeline | resume_from_passport | High | — |
| `/arg-paper` | academic-paper | full | High | ~$3–4 |
| `/arg-plan` | academic-paper | plan | Very High | ~$0.50 |
| `/arg-outline` | academic-paper | outline-only | High | ~$0.30 |
| `/arg-lit-review` | academic-paper | lit-review | Medium | ~$0.50–1 |
| `/arg-abstract` | academic-paper | abstract-only | Medium | ~$0.20 |
| `/arg-revision` | academic-paper | revision | High | ~$1–2 |
| `/arg-revision-coach` | academic-paper | revision-coach | Medium | ~$0.30 |
| `/arg-citation-check` | academic-paper | citation-check | Low | ~$0.20 |
| `/arg-format-convert` | academic-paper | format-convert | Low | ~$0.20 |
| `/arg-disclosure` | academic-paper | disclosure | Low | ~$0.10 |
| `/arg-diagram` | academic-paper | diagram | Medium | ~$0.20 |
| `/arg-deep-research` | deep-research | full | High | ~$1–2 |
| `/arg-deep-research-quick` | deep-research | quick | Medium | ~$0.20 |
| `/arg-deep-research-review` | deep-research | review | High | ~$0.50 |
| `/arg-deep-research-lit-review` | deep-research | lit-review | Medium | ~$0.50–1 |
| `/arg-deep-research-fact-check` | deep-research | fact-check | Medium | ~$0.30 |
| `/arg-deep-research-socratic` | deep-research | socratic | Very High | ~$0.50 |
| `/arg-deep-research-systematic-review` | deep-research | systematic-review | Medium | ~$2–3 |
| `/academic-paper-reviewer` | academic-paper-reviewer | full | High | ~$1–2 |
| `/arg-reviewer-re-review` | academic-paper-reviewer | re-review | Medium | ~$0.50 |
| `/arg-reviewer-quick` | academic-paper-reviewer | quick | Low | ~$0.30 |
| `/arg-reviewer-methodology` | academic-paper-reviewer | methodology-focus | Medium | ~$0.50 |
| `/arg-reviewer-guided` | academic-paper-reviewer | guided | Very High | ~$0.50 |
| `/arg-reviewer-calibration` | academic-paper-reviewer | calibration | Medium | ~$0.30× N |
