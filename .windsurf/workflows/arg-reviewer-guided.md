---
description: ARG academic-paper-reviewer guided mode — Socratic issue-by-issue guided review dialogue
---

Trigger the `academic-paper-reviewer` skill in `guided` mode. Helps authors understand problems themselves through progressive revelation and Socratic dialogue. Originality-spectrum, very-high oversight.

1. Read the skill entry at `academic-paper-reviewer/SKILL.md` and locate the `guided` mode section.
2. Read `academic-paper-reviewer/references/guided_mode_protocol.md` for dialogue flow, progressive revelation rules, and sequence.
3. Read `MODE_REGISTRY.md` § academic-paper-reviewer for mode details.
4. Run all 5 reviewers internally (same as `full` mode) to build a complete issue map — do NOT reveal the full report to the user upfront.
5. Run Socratic guided dialogue:
   - Open with 2–3 genuine strengths of the paper.
   - Introduce issues one at a time in severity order (highest first), using questions rather than declarations.
   - For each issue: ask the user what they think the problem is before explaining it.
   - Guide the user to self-identify the fix where possible.
   - Progress through methodology → domain → perspective → DA issues in sequence.
6. After all issues are surfaced, produce:
   - User's self-formulated revision strategy (summarise what the user said).
   - Reprioritised Revision Roadmap based on dialogue.
7. The user can say "just show me the full review" at any point to exit guided mode and receive the standard `full` mode output.
