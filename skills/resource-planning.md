---
type: skill
id: resource-planning
title: Resource Planning
description: "Planning resource allocation across teams and quarters, identifying gaps, conflicts, and capacity constraints"
tags: [Production, Tested, Citations, Planning]
connections:
  - target: llm-service
    type: runs_on
metadata:
  estimated_duration: "5-8 minutes"
  avg_tokens: 2500
  trigger: manual
---

## Resource Planning

This skill enables the mapping of product initiatives to available teams and resources, identifying allocation conflicts, capacity gaps, and skill shortages before they become execution problems. A roadmap that ignores resource constraints is a wish list; a roadmap that accounts for them is a plan.

### Core Capabilities

#### Team Capacity Modelling

Before allocating initiatives to teams, establish the actual available capacity:

**Headcount to capacity conversion:**
- Start with total headcount by function (engineering, design, product, QA)
- Subtract planned absences: holidays, training, conferences, parental leave
- Subtract operational overhead: on-call rotation, support escalations, production incidents, code reviews for other teams
- Subtract organisational overhead: all-hands, team meetings, 1:1s, planning ceremonies
- The remaining capacity is typically 60-70% of total headcount. For a team of 6 engineers, effective capacity is approximately 4 engineer-equivalents.

**Skill-weighted capacity:**
- Not all engineers are interchangeable. A backend initiative cannot be staffed by a frontend specialist.
- Map each team member's primary skills and secondary skills
- When allocating work, match initiative requirements to available skills
- If an initiative requires a skill that only one person has, that person is a single point of failure — flag this risk

**Velocity calibration:**
- If historical velocity data is available (story points per sprint, features shipped per quarter), use it to calibrate capacity estimates
- If a team historically delivers 80% of what they plan, apply a 0.8 velocity factor
- Avoid the temptation to assume "this quarter will be different" — unless something material has changed (new hire, removed overhead, reduced scope), it will not be different

#### Resource Allocation Process

##### Step 1: Demand Mapping

For each initiative on the roadmap, list:
- The team(s) required
- The specific skills needed
- The estimated effort by function
- The quarter(s) in which the work is planned

##### Step 2: Supply Matching

For each team, for each quarter:
- Total available capacity (after overhead adjustments)
- Initiatives allocated to that team
- Total effort committed vs. total capacity available
- Utilisation rate: committed effort / available capacity

**Target utilisation:** 70-85% is healthy. Below 70% suggests over-hiring or insufficient ambition. Above 85% leaves no room for unplanned work, production incidents, or supporting other teams. Above 100% means the plan is infeasible.

##### Step 3: Conflict Resolution

When demand exceeds supply:

1. **Re-sequence:** Can initiatives be moved to a different quarter to smooth demand? Check that dependency constraints allow this.
2. **Re-assign:** Can a different team take on some of the work? This works when the skills are transferable, but watch out for context-switching costs.
3. **Reduce scope:** Can an initiative be descoped to reduce effort while preserving the core value? This is often the best option for medium-priority initiatives.
4. **Defer:** Can an initiative be moved to a later quarter or removed from the roadmap entirely?
5. **Add resources:** Can the team be expanded (new hire, contractor, borrowed engineer)? This is typically the slowest option — new hires take 2-3 months to reach productivity.

Present conflicts and proposed resolutions to stakeholders; do not resolve them silently.

##### Step 4: Gap Analysis

Identify situations where:
- **No team exists** for a required capability (e.g., machine learning expertise needed but no ML team)
- **Critical skills are concentrated** in one person (key person risk)
- **Teams are consistently over-allocated** across multiple quarters (structural understaffing)
- **Important themes have no resource allocation** (strategic priorities that are unfunded)

Each gap should include a recommendation: hire, train, contract, partner, or defer.

#### Cross-Team Dependencies

The most difficult resource planning challenge is cross-team work:

- When two teams must collaborate on an initiative, coordination overhead is significant (typically 20-30% of total effort)
- Handoff points between teams are common failure points — specify interfaces clearly
- If team A must complete a component before team B can start, the calendar time is sequential, not parallel
- Consider dedicating a "glue person" (typically a product manager or tech lead) to coordinate cross-team initiatives

#### Communicating Resource Plans

Resource allocation data should be presented in three formats:

1. **Team view:** For each team, what are they working on each quarter? What is their utilisation? Where are the conflicts?
2. **Initiative view:** For each initiative, which teams are involved? Are they available? What are the risks?
3. **Gap view:** Where does the roadmap require resources that are not currently available? What is the plan to close these gaps?

### Constraints

- Never present a plan where any team exceeds 100% utilisation — this is a plan that cannot be executed
- Always include a buffer for unplanned work (15-20% of capacity) — production will always generate surprises
- If resource allocation requires a new hire, include realistic ramp-up time (2-3 months for a new engineer to reach full productivity)
- Surface single points of failure (key person dependencies) as risks, not just footnotes
- Re-validate resource allocation whenever the roadmap changes — initiative additions or scope changes require resource recalculation
