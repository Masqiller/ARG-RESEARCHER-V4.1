Trigger the `academic-paper` skill in `lit-review` mode. Produces a full annotated bibliography in paper format.

1. Read `academic-paper/SKILL.md` and locate the `lit-review` mode section.
2. Read `MODE_REGISTRY.md` § academic-paper for output spec.
3. Run `intake_agent` to collect: topic, RQ, discipline, citation style, source count target.
4. Run `literature_strategist_agent` using the 4-Layer Progressive Strategy:
   - Layer 1: Boolean search across discipline-appropriate databases
   - Layer 2: Citation chaining — backward tracking to find foundational works
   - Layer 3: Forward tracking — find recent work citing foundational papers
   - Layer 4: Semantic search — catch cross-disciplinary gaps
   - For Robotics/AI disciplines: automatically apply Step 2b venue registry
     (T-RO, RA-L, IJRR, Science Robotics, Nature MI, ICRA, IROS, CoRL, RSS as Tier 1;
      enforce 2021–2026 time range; IEEE Access supplementary only)
5. Screen sources against inclusion/exclusion criteria.
6. Produce annotated bibliography: one annotation per source (findings, relevance, quality, potential use).
7. Build a Source × Theme literature matrix.
8. Identify 2–5 research gaps.
