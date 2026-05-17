# Mermaid Pattern Library — Secondary Engine Templates for `diagram_master_agent`

> **Restricted use only.** Mermaid is a secondary engine. Use ONLY when:
> - (a) Output is Markdown-only and LaTeX is NOT required
> - (b) User requests a quick draft/preview before LaTeX finalization
> - (c) Diagram type is sequence or state machine and TikZ overhead is unjustified
>
> For LaTeX papers, always prefer TikZ patterns from `diagram_tikz_patterns.md`.
> Always add: `<!-- Mermaid draft — generate TikZ for final LaTeX -->`

---

## Pattern 1 — Methodology / Process Flowchart

**Permitted**: Markdown output only.  
**For LaTeX**: Use TikZ Pattern 1 from `diagram_tikz_patterns.md`.

````markdown
<!-- Figure D[N]: [Title] -->
<!-- diagram_master_agent (Dr. Atlas) | Category 1/3 | Engine: Mermaid (draft) -->
<!-- Mermaid draft — generate TikZ for final LaTeX -->

```mermaid
---
title: [Research/Process Flow Title]
---
flowchart TD
    A([Start]) --> B[Phase 1: Literature Review]
    B --> C{Methodology\nSelection}
    C -->|Quantitative| D[Survey Design]
    C -->|Qualitative| E[Interview Protocol]
    C -->|Mixed| F[Sequential\nExplanatory]
    D --> G[Data Collection]
    E --> G
    F --> G
    G --> H[Analysis]
    H --> I{Sufficient\nEvidence?}
    I -->|Yes| J[Findings]
    I -->|No| B
    J --> K([End])

    style A fill:#001f3f,color:#fff,stroke:#001f3f
    style K fill:#001f3f,color:#fff,stroke:#001f3f
    style C fill:#008080,color:#fff,stroke:#008080
    style I fill:#008080,color:#fff,stroke:#008080
```

**Figure [N].** [Caption text.]
````

---

## Pattern 2 — Sequence Diagram

**Permitted**: Mermaid acceptable when TikZ overhead is unjustified (≤10 messages).

````markdown
<!-- Figure D[N]: [Title] -->
<!-- diagram_master_agent (Dr. Atlas) | Category 5 | Engine: Mermaid -->

```mermaid
---
title: [Interaction Sequence Title]
---
sequenceDiagram
    autonumber
    participant U as User
    participant S as System
    participant D as Database
    participant E as External API

    U->>S: Submit request
    activate S
    S->>D: Query data
    activate D
    D-->>S: Return results
    deactivate D
    S->>E: Fetch metadata
    activate E
    E-->>S: Metadata response
    deactivate E
    S-->>U: Display output
    deactivate S

    Note over S,D: Internal processing
    Note right of E: Rate-limited to 100 req/min
```

**Figure [N].** [Caption text.]
````

---

## Pattern 3 — State Machine / FSM

**Permitted**: Mermaid acceptable for simple state diagrams (≤8 states).  
**For complex state machines**: Use TikZ Pattern 6 (automata) instead.

````markdown
<!-- Figure D[N]: [Title] -->
<!-- diagram_master_agent (Dr. Atlas) | Category 12 | Engine: Mermaid -->

```mermaid
---
title: [System State Machine Title]
---
stateDiagram-v2
    [*] --> Idle
    Idle --> Active : initialize
    Active --> Processing : trigger_event
    Processing --> Success : valid_result
    Processing --> Error : invalid_input
    Error --> Active : retry
    Error --> Failed : max_retries_exceeded
    Success --> Idle : reset
    Failed --> [*]

    note right of Processing : Async operation\ntimeout: 30s
    note left of Error : Logged to audit trail
```

**Figure [N].** [Caption text.]
````

---

## Pattern 4 — Gantt / Timeline (Draft Only)

**Permitted**: Markdown draft or quick preview only.  
**For final paper**: Use TikZ Pattern 7 (timeline).

````markdown
<!-- Figure D[N]: [Title] -->
<!-- diagram_master_agent (Dr. Atlas) | Category 11 | Engine: Mermaid (draft only) -->
<!-- Mermaid draft — generate TikZ for final LaTeX -->

```mermaid
---
title: Research Timeline
---
gantt
    dateFormat  YYYY-MM
    axisFormat  %Y-%m
    section Phase 1
    Literature Review      :p1, 2024-01, 3M
    Protocol Development   :p2, after p1, 2M
    section Phase 2
    Data Collection        :p3, after p2, 4M
    Data Analysis          :p4, after p3, 3M
    section Phase 3
    Writing                :p5, after p4, 3M
    Revision               :p6, after p5, 2M
```

**Figure [N].** [Caption text. Note: timeline is approximate.]
````

---

## Pattern 5 — Decision Tree / Classification Flow

**Permitted**: Markdown output only.

````markdown
<!-- Figure D[N]: [Title] -->
<!-- diagram_master_agent (Dr. Atlas) | Category 3 | Engine: Mermaid (draft) -->
<!-- Mermaid draft — generate TikZ for final LaTeX -->

```mermaid
---
title: [Decision / Classification Tree Title]
---
flowchart TD
    Root{Root Criterion} -->|Condition A| B[Branch A]
    Root -->|Condition B| C[Branch B]
    Root -->|Condition C| D[Branch C]

    B -->|Sub-A1| B1[Leaf B1]
    B -->|Sub-A2| B2[Leaf B2]
    C -->|Sub-B1| C1[Leaf C1]
    C -->|Sub-B2| C2[Leaf C2]
    D --> D1[Leaf D1]

    subgraph Group_1 [Group Label 1]
        B1
        B2
    end

    subgraph Group_2 [Group Label 2]
        C1
        C2
    end

    style Root fill:#008080,color:#fff,stroke:#008080
```

**Figure [N].** [Caption text.]
````

---

## Mermaid Usage Checklist

Before generating any Mermaid diagram, confirm:

- [ ] Output format is confirmed Markdown-only (not LaTeX) OR user explicitly requested draft/preview
- [ ] Mermaid draft comment added: `<!-- Mermaid draft — generate TikZ for final LaTeX -->`
- [ ] Title block present (`---\ntitle: ...\n---`)
- [ ] All node IDs are unique
- [ ] All edge targets reference existing nodes
- [ ] Node labels ≤ 5 words
- [ ] Total nodes ≤ 30
- [ ] Consistent arrow types within same relationship category
- [ ] `style` overrides use hex colors from the academic palette
