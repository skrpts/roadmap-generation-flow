---
type: prompt
id: dependency-graph-generator
title: Dependency Graph Generator
description: "Generate a dependency graph narrative and matrix for a set of product initiatives, identifying critical paths and sequencing constraints"
tags: [Production, Planning, Communication]
connections:
  - target: dependency-mapping
    type: derived_from
  - target: timeline-calculator
    type: uses
metadata:
  estimated_duration: "5-8 minutes"
  avg_tokens: 3500
  trigger: manual
---

## Dependency Graph Generator

You are a technical programme manager. Your task is to analyse a set of product initiatives and produce a complete dependency map — identifying which initiatives depend on which, the nature and strength of each dependency, the critical path, and sequencing recommendations.

### Input

**Initiatives (from Initiative Breakdown stage):**
{{steps.Theme Extraction.output}}

Use the technical architecture context, team structure, and existing commitments from the initiative breakdown to inform dependency identification and sequencing constraints.

### Instructions

#### Phase 1: Pairwise Dependency Analysis

For every pair of initiatives, assess whether a dependency exists. For each identified dependency, document:

1. **Direction:** Which initiative depends on which (A depends on B, or bidirectional)
2. **Type:**
   - **Hard technical:** A literally cannot be built without B's output (API, data pipeline, infrastructure)
   - **Soft technical:** A can proceed without B but with increased effort or reduced quality
   - **Business:** A's value depends on B's success (e.g., monetisation depends on adoption)
   - **Resource:** A and B require the same team or specialist
   - **Knowledge:** A's design depends on learnings from B
3. **Strength:**
   - **Blocking:** A cannot start or complete until B reaches a defined state
   - **Constraining:** A can proceed but is significantly harder or less valuable without B
   - **Preferential:** B-before-A is desirable but not required

Focus especially on:
- Cross-team dependencies (these are most often missed and most impactful)
- Data dependencies (who produces data that others consume?)
- Shared component dependencies (who is modifying shared code or infrastructure?)
- External dependencies (regulatory approvals, partner deliverables, vendor timelines)

#### Phase 2: Critical Path Identification

From the blocking dependencies, construct the critical path:

1. Build a directed acyclic graph (DAG) of all blocking dependencies
2. If the graph contains cycles, flag each cycle as a problem requiring initiative re-scoping
3. Calculate the total estimated duration of each path through the graph (sum of initiative effort estimates)
4. The longest path is the critical path — it determines the minimum possible timeline
5. Identify near-critical paths (within 20% of the critical path duration) — delays on these could also cascade

#### Phase 3: Risk Assessment

Analyse the dependency structure for concentrated risk:

- **High fan-out nodes:** Initiatives that many others depend on. A delay here affects multiple downstream initiatives. List the top 3 by fan-out count.
- **High fan-in nodes:** Initiatives that depend on many prerequisites. These are vulnerable to delays in any prerequisite. List the top 3 by fan-in count.
- **Long chains:** Dependency chains of 4+ initiatives where each link depends on the previous. Each link adds probability of delay.
- **Single points of failure:** Initiatives where only one team or person has the required expertise.
- **External bottlenecks:** Dependencies on external parties (vendors, partners, regulators) where the team has limited ability to accelerate.

#### Phase 4: Sequencing Recommendation

Based on the dependency analysis, propose an execution sequence:

1. **Immediate starts:** Initiatives with zero blocking dependencies — these can begin immediately
2. **Phase 2:** Initiatives whose only dependencies are on immediate-start items
3. **Phase 3+:** Continue until all initiatives are sequenced
4. Within each phase, indicate which initiatives can run in parallel
5. Highlight where resource dependencies create sequencing constraints beyond what the technical dependencies require

### Output Format

**1. Dependency matrix:**

A table with initiatives on both axes, cells indicating dependency type and strength:

| | Init A | Init B | Init C | Init D |
|---|---|---|---|---|
| **Init A** | — | Hard/Blocking | — | Soft/Constraining |
| **Init B** | — | — | — | — |
| **Init C** | Resource/Blocking | — | — | Hard/Blocking |
| **Init D** | — | — | — | — |

Read as: row depends on column (Init A depends on Init B with a hard blocking dependency).

**2. Critical path narrative:**

A written description of the critical path: which initiatives form it, what their total duration is, where the highest risk lies, and what the consequences of delay would be.

**3. Risk summary:**

Top 5 dependency risks ranked by potential impact, each with:
- Description of the risk
- Initiatives affected
- Probability assessment (high/medium/low)
- Mitigation recommendation

**4. Sequencing plan:**

A phased execution plan showing which initiatives can start when, considering both technical and resource dependencies.

**5. Circular dependency flags:**

Any identified cycles, with a recommendation for how to break them (typically by re-scoping one of the initiatives).

### Constraints

- Only hard/blocking dependencies should constrain the timeline. Do not treat preferences as requirements.
- If you identify more than 3 circular dependencies, the initiative set needs re-scoping before the roadmap can proceed.
- Cross-team dependencies must be explicitly called out — they are the most common source of roadmap delays.
- External dependencies must include a realistic timeline assessment, not an optimistic one.
- If the dependency graph is too dense (more than 60% of possible dependencies exist), the initiatives are not sufficiently decomposed.
