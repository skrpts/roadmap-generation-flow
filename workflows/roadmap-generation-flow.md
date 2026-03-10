---
type: workflow
id: roadmap-generation-flow
title: Roadmap Generation Flow
description: "Comprehensive multi-stage pipeline that generates a complete product roadmap from vision, OKRs, and customer feedback through themed initiatives, dependency mapping, resource allocation, and stakeholder-ready output"
tags: [Production, Tested]
connections:
  - target: theme-extraction
    type: uses
  - target: dependency-mapping
    type: uses
  - target: timeline-estimation
    type: uses
  - target: resource-planning
    type: uses
  - target: vision-to-themes-prompt
    type: uses
  - target: initiative-breakdown-prompt
    type: uses
  - target: dependency-graph-generator
    type: uses
  - target: timeline-calculator
    type: uses
  - target: resource-mapper
    type: uses
  - target: roadmap-narrative-writer
    type: uses
  - target: roadmap-assembler
    type: uses
  - target: claude-service
    type: runs_on
  - target: roadmap-methodology-guide
    type: references
  - target: roadmap-governance-framework
    type: references
  - target: roadmap-communication-guide
    type: references
  - target: roadmap-template
    type: references
  - target: quarterly-planning-template
    type: references
metadata:
  estimated_duration: "30-50 minutes"
  avg_tokens: 25000
  trigger: manual
---

## Roadmap Generation Flow

This is a comprehensive, seven-stage pipeline that generates a complete product roadmap from strategic inputs (vision, OKRs, customer feedback, market analysis) through to a stakeholder-ready document with themed initiatives, dependency graphs, realistic timelines, resource allocation plans, and a compelling narrative. It is the most complex workflow in the product-manager skrpt collection and is designed to produce a roadmap that can be presented directly to executives, shared with cross-functional partners, and used to guide quarterly planning.

### Prerequisites

Before running this pipeline, gather the following inputs:

**Required:**
- Product vision statement (1-2 paragraphs describing where the product is heading)
- Current OKRs or strategic priorities (company-level and product-level)
- Known customer problems and feedback themes (from research, support tickets, sales conversations)

**Strongly recommended:**
- Current product metrics (adoption, engagement, retention, revenue)
- Competitive landscape analysis (key competitors, their recent moves, your differentiation)
- Technical architecture context (major systems, known limitations, tech debt areas)
- Team composition and capacity (headcount by function, skill gaps, contractor availability)
- Existing commitments (contractual obligations, regulatory deadlines, partnership milestones)

**Optional but valuable:**
- Customer segmentation data (who uses what, and how)
- Previous roadmap (for continuity and retrospective assessment)
- Market research or analyst reports
- Board or investor expectations

### Pipeline Stages

#### Stage 1: Vision to Themes

**Node:** `vision-to-themes-prompt`
**Skill:** `theme-extraction`
**References:** `roadmap-methodology-guide`

This is the strategic foundation. Take the vision, OKRs, and customer feedback and distil them into 4-7 strategic themes that will organise the roadmap.

Process:
1. Analyse the product vision to identify the key value propositions and strategic directions
2. Map current OKRs to potential theme areas
3. Cluster customer feedback and problems into thematic groups
4. Identify themes that emerge across multiple input sources (vision + OKRs + feedback convergence)
5. Validate that each theme is distinct, actionable, and clearly connected to at least one strategic priority
6. Name each theme clearly — a good theme name communicates the strategic intent (e.g., "Enterprise Readiness" not "Feature Category B")
7. Write a 2-3 sentence description for each theme explaining what it covers and why it matters

Output: 4-7 named strategic themes with descriptions and source mapping.

**Error handling:** If the vision is too vague to extract meaningful themes, return a set of clarifying questions. If OKRs and customer feedback point in contradictory directions, surface this tension explicitly rather than forcing alignment.

#### Stage 2: Initiative Breakdown

**Node:** `initiative-breakdown-prompt`
**Skill:** `theme-extraction`

For each strategic theme, break it down into 3-6 concrete, scoped initiatives.

Process:
1. For each theme, brainstorm the specific initiatives that would advance it
2. Scope each initiative to be deliverable within a single quarter (if an initiative is larger, decompose it further)
3. Define clear outcomes for each initiative — what does "done" look like, and how will success be measured?
4. Classify each initiative's strategic role: table stakes (must have to compete), differentiator (creates competitive advantage), or bet (high risk, high potential reward)
5. Estimate the confidence level for each initiative's expected outcome: high (validated), medium (reasonable hypothesis), low (speculative)
6. Map each initiative to the customer segment(s) it primarily serves

Output: 15-35 scoped initiatives organised by theme, each with defined outcomes, strategic classification, and confidence level.

**Error handling:** If a theme cannot be broken into at least 3 concrete initiatives, it may be too narrow — consider merging it with a related theme. If a theme produces more than 8 initiatives, it may be too broad — consider splitting it.

#### Stage 3: Dependency Mapping

**Node:** `dependency-graph-generator`
**Skill:** `dependency-mapping`

Map the technical and business dependencies between initiatives.

Process:
1. For each initiative, identify what it depends on (prerequisites) and what depends on it (downstream)
2. Classify dependency types:
   - **Hard technical dependency:** Initiative B cannot start until Initiative A is complete (e.g., API must exist before client can consume it)
   - **Soft technical dependency:** Initiative B benefits from Initiative A but can proceed with workarounds
   - **Business dependency:** Initiative B's value proposition depends on Initiative A's success (e.g., premium features only matter if the free tier drives adoption)
   - **Resource dependency:** Initiative A and B require the same team or specialist, creating a sequencing constraint
3. Identify dependency chains — sequences of 3+ initiatives where each depends on the previous
4. Flag circular dependencies (A depends on B depends on A) — these indicate a design problem
5. Identify the critical path — the longest chain of hard dependencies that determines the minimum timeline
6. Highlight initiatives with zero dependencies (can start immediately) and initiatives that are heavily depended upon (high risk if delayed)

Output: A dependency narrative and structured dependency matrix showing all relationships.

**Error handling:** If the dependency graph is too complex (more than 50% of initiatives have hard dependencies on each other), this suggests the initiatives are not sufficiently decomposed. Recommend further breakdown.

#### Stage 4: Timeline Calculation

**Node:** `timeline-calculator`
**Skill:** `timeline-estimation`

Estimate realistic timelines for each initiative, accounting for complexity, dependencies, and historical velocity.

Process:
1. For each initiative, estimate the effort in person-weeks (not calendar weeks) broken down by function: engineering, design, product, QA
2. Apply a realism multiplier based on complexity and uncertainty:
   - Well-understood work with precedent: 1.2x (20% buffer)
   - Moderately complex or novel work: 1.5x (50% buffer)
   - Highly uncertain or first-of-kind work: 2.0x (100% buffer)
3. Convert effort estimates to calendar timelines using team capacity (accounting for meetings, support rotation, holidays, on-call duties — typically 60-70% of total time is available for project work)
4. Sequence initiatives based on the dependency graph, placing independent initiatives in parallel where capacity allows
5. Assign initiatives to quarters (or months, for shorter planning horizons)
6. Identify the initiatives that fall outside the planning horizon — these form the "later" or "future" category
7. Stress-test the timeline: what happens if the highest-risk initiative takes 2x longer than estimated? Does it cascade?

Output: A time-bound initiative plan with quarter assignments, effort estimates, and confidence levels.

**Error handling:** If the total effort exceeds available capacity by more than 20%, flag this immediately. The timeline is unrealistic and the roadmap needs to be trimmed or resources need to be added. Do not present an impossible timeline as a plan.

#### Stage 5: Resource Mapping

**Node:** `resource-mapper`
**Skill:** `resource-planning`
**References:** `quarterly-planning-template`

Map initiatives to teams and identify resource gaps, conflicts, and allocation decisions.

Process:
1. For each initiative, identify the team(s) required and the key skills needed
2. Map initiatives to available teams and individuals
3. Calculate utilisation per team per quarter — are any teams over-allocated?
4. Identify resource conflicts — initiatives competing for the same team's time
5. Flag skill gaps — initiatives requiring capabilities the current team does not have
6. Propose resolution options for conflicts and gaps:
   - Re-sequence initiatives to smooth resource demand
   - Identify initiatives that can be handed to a different team
   - Flag where hiring, contracting, or upskilling is needed
   - Identify initiatives that should be cut if resources cannot be secured
7. Produce a per-quarter resource allocation summary

Output: A resource allocation plan showing team-by-team assignments, utilisation rates, conflicts, and proposed resolutions.

**Error handling:** If resource allocation reveals that more than 30% of planned initiatives cannot be staffed, the roadmap is aspirational, not executable. Clearly distinguish between "planned and staffed" initiatives and "planned but unfunded" initiatives.

#### Stage 6: Narrative Writing

**Node:** `roadmap-narrative-writer`
**Skills:** `theme-extraction`, `dependency-mapping`, `timeline-estimation`, `resource-planning`
**References:** `roadmap-communication-guide`

Write a compelling roadmap narrative that connects the strategic themes, initiative choices, and timeline to the product vision.

Process:
1. Open with the strategic context: where the product is today, where it is heading, and why
2. Present each theme as a chapter in the product's story — not a list of features, but a strategic direction with rationale
3. Highlight the key trade-offs made: what was prioritised, what was deferred, and why
4. Address the critical path: what are the most important initiatives and what happens if they slip?
5. Present the resource allocation story: the team is right-sized for this plan / the team needs growth in these areas
6. Include a confidence assessment: which parts of the roadmap are high-confidence (validated need, understood implementation) and which are bets (unvalidated hypothesis, novel technology)?
7. Close with what success looks like: if this roadmap is executed well, what does the product look like in 12 months?

Output: A 1,000-2,000 word roadmap narrative suitable for stakeholder presentation.

**Error handling:** If the narrative reveals logical gaps (themes that do not connect to vision, initiatives that do not connect to themes), surface these rather than papering over them.

#### Stage 7: Document Assembly

**Node:** `roadmap-assembler`
**References:** `roadmap-template`

Assemble all components into a complete, structured roadmap document.

Process:
1. Compile the roadmap narrative as the opening section
2. Present the theme overview with initiative roll-ups
3. Include the timeline visualisation (quarter-by-quarter initiative plan)
4. Include the dependency map (narrative and matrix formats)
5. Include the resource allocation summary
6. Append the detailed initiative cards (one per initiative with scope, outcomes, timeline, team, dependencies, risks)
7. Include a governance section: review cadence, change process, escalation path
8. Add an executive summary at the very beginning (200-300 words covering the key themes, timeline, resource needs, and asks)

Output: A complete roadmap document ready for stakeholder review.

### Output

The final roadmap document contains:

1. **Executive summary** — 200-300 word overview of the roadmap's key elements
2. **Strategic narrative** — the story of where the product is heading and why
3. **Theme overview** — 4-7 strategic themes with descriptions and initiative counts
4. **Initiative plan** — all initiatives organised by theme, with quarter assignments
5. **Dependency map** — narrative and matrix showing initiative relationships
6. **Timeline** — quarter-by-quarter plan with effort estimates and confidence levels
7. **Resource allocation** — team-by-team assignments with utilisation and gap analysis
8. **Initiative cards** — detailed cards for each initiative (scope, outcomes, team, risks)
9. **Governance framework** — review cadence, change process, decision authority
10. **Appendices** — raw data, methodology notes, assumptions register

### Error Handling

- **Vague vision:** Return clarifying questions; a roadmap without a clear vision is a feature list without direction
- **Insufficient data:** Proceed with clearly flagged assumptions and lower confidence levels rather than blocking entirely
- **Capacity overcommitment:** Flag immediately and present trade-off options (cut scope, extend timeline, add resources)
- **Contradictory priorities:** Surface the contradiction for stakeholder resolution rather than making an arbitrary choice
- **Circular dependencies:** Flag as a design problem requiring initiative re-scoping before the roadmap can be finalised
- **Stale inputs:** If the strategic context or metrics are more than one quarter old, warn that the roadmap may not reflect current reality
