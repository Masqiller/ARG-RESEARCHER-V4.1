Trigger the `academic-pipeline` orchestrator. Executes the complete 10-stage academic research workflow.

1. Read `academic-pipeline/SKILL.md` for full pipeline stages.
2. Read `MODE_REGISTRY.md` § academic-pipeline for mode details.
3. Read `shared/handoff_schemas.md` for the Material Passport handoff protocol.
4. Execute the 10-stage pipeline:
   - Stage 1: Deep research (literature search, source verification, synthesis)
   - Stage 2: Academic paper drafting (IMRaD or domain-appropriate structure)
     - Phase 2D (parallel with argument building): invoke `diagram_master_agent` Planner mode
       → Read `academic-paper/agents/diagram_master_agent.md` and `academic-paper/references/diagram_taxonomy.md`
       → Scan outline for diagram opportunities; score and present Diagram Plan to user
     - Phase 4 (drafting): invoke `diagram_master_agent` Generator mode for each diagram with score ≥ 4
       → Generate TikZ/Mermaid/PGFPlots code; embed inline in draft with \caption and \label
       → Inject required preamble packages; add in-text figure references
     - Phase 5c (parallel with citation check and abstract): invoke `diagram_master_agent` Validator mode
       → Run syntax, package, label, cross-reference, and caption-citation checks
       → Produce Diagram Audit Report; flag caption citations to `citation_compliance_agent`
   - Stage 2.5: Integrity checkpoint (compliance agent; includes diagram code in verification scope)
   - Stage 3: Peer review (5-reviewer panel + editorial synthesis)
   - Stage 4: Revision (point-by-point response to reviewers)
   - Stage 4.5: Final integrity checkpoint
   - Stage 5: Re-review (max 2 loops)
   - Stage 6: Format conversion + finalization
   - Process Summary + AI Self-Reflection Report
5. Follow all citation protocols (Two-Layer v3.7.1 + Three-Layer v3.7.3).
6. Include AI disclosure statement in all outputs.
