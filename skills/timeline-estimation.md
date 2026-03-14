---
type: skill
id: timeline-estimation
title: Timeline Estimation
description: "Estimating realistic timelines for product initiatives accounting for complexity, risk, capacity, and historical velocity"
tags: [Production, Tested]
connections:
  - target: llm-service
    type: runs_on
metadata:
  estimated_duration: "5-8 minutes"
  avg_tokens: 2500
  trigger: manual
---

## Timeline Estimation

This skill enables the estimation of realistic timelines for product initiatives. "Realistic" is the operative word — timeline estimation is not about optimistic aspiration or pessimistic padding, but about producing estimates that the team can commit to with reasonable confidence.

### Core Capabilities

#### Effort Estimation

Before estimating calendar time, estimate effort — the total amount of work required regardless of how many people are assigned.

**Functional breakdown:**
- **Product/design effort:** Requirements definition, design exploration, prototyping, user testing, specification writing
- **Engineering effort:** Implementation, code review, testing, documentation, deployment
- **QA effort:** Test planning, test execution, regression testing, performance testing
- **Rollout effort:** Feature flagging, staged rollout, monitoring, documentation updates

**Estimation techniques:**

1. **Analogous estimation:** Compare to similar work completed previously. "The last API integration took 6 weeks with a team of 3; this one is comparable in scope." This is the most reliable method when good analogues exist.

2. **Bottom-up estimation:** Decompose the initiative into tasks, estimate each task, and sum. This is precise but time-consuming and tends to miss integration and coordination overhead.

3. **Three-point estimation:** For each initiative, estimate the optimistic (O), most likely (M), and pessimistic (P) durations. Calculate the expected duration as (O + 4M + P) / 6. This accounts for uncertainty without requiring false precision.

4. **T-shirt sizing:** For early-stage roadmapping where precision is neither possible nor necessary: S (1-2 weeks), M (3-6 weeks), L (7-12 weeks), XL (13+ weeks). Convert to specific estimates only when the initiative enters active planning.

#### From Effort to Calendar Time

Effort and calendar time are not the same. Key adjustments:

**Capacity factor:** Engineers do not code 40 hours per week. Meetings, code reviews, support rotation, on-call duties, and administrative tasks typically consume 30-40% of available time. Apply a capacity factor of 0.6-0.7 to convert person-hours of effort to person-hours of calendar time.

**Team size factor:** Adding people does not proportionally reduce calendar time. Communication overhead scales with team size. For teams of 2-3, assume 90% parallel efficiency. For teams of 4-6, assume 75%. For teams of 7+, assume 60% and consider decomposing the initiative.

**Dependency wait time:** If an initiative depends on another that is not yet complete, add the expected wait time. Do not assume dependencies will be resolved on time — if the dependency has a 30% chance of being late, factor in the expected delay.

**Review and approval cycles:** Design reviews, architecture reviews, security reviews, and stakeholder approvals each add calendar time. Estimate 3-5 business days per review cycle, and 1-2 review cycles per initiative.

#### Realism Multipliers

Apply a realism multiplier based on the initiative's uncertainty profile:

| Condition | Multiplier | Rationale |
|-----------|-----------|-----------|
| Well-understood problem, experienced team, clear requirements | 1.2x | Minimal unknowns; buffer for minor surprises |
| Familiar domain but new approach or technology | 1.5x | Known unknowns that will require investigation |
| New domain, new technology, or unclear requirements | 2.0x | Significant unknowns; likely to discover scope during implementation |
| First-of-kind work with no precedent | 2.5-3.0x | Unknown unknowns; treat as a research project with delivery aspirations |

These multipliers are not padding — they are corrections for the well-documented tendency of software teams to underestimate by 50-200%.

#### Timeline Validation

After producing timeline estimates:

1. **Gut check:** Does the timeline feel right to people with relevant experience? If the estimate says 2 weeks but experienced engineers are uncomfortable, listen to the discomfort.

2. **Historical comparison:** How does this compare to similar past work? If the estimate is significantly faster than historical performance, the burden of proof is on the estimate.

3. **Constraint check:** Does the timeline fit within the planning horizon? If a quarter's roadmap contains 18 months of work, the timeline is a wish, not a plan.

4. **Dependency cascade check:** If the highest-risk initiative on the critical path takes 2x longer than estimated, what happens to the overall timeline? If the roadmap collapses, the estimates are too tight.

5. **Resource check:** Does the timeline assume resources that are not yet secured (a new hire, a contractor, a team transfer)? If so, add the expected lead time for securing those resources.

### Confidence Levels

Assign a confidence level to each timeline estimate:

- **High (80%+ likelihood):** Based on analogous past work with a similar team, clear requirements, and well-understood technology
- **Medium (50-80% likelihood):** Based on reasonable assumptions with some uncertainties, new technology or new team composition
- **Low (<50% likelihood):** Based on speculation, novel work, unclear requirements, or unvalidated assumptions

Low-confidence estimates should be flagged prominently in the roadmap and accompanied by a note on what would increase confidence (e.g., "confidence would increase to Medium after a 2-week technical spike").

### Constraints

- Never present a single-point estimate as precise — always communicate the uncertainty range
- Never assume perfect parallelism when adding team members — account for communication overhead
- Always disclose the assumptions underlying the estimate
- If the total estimated effort exceeds available capacity, say so immediately rather than presenting an infeasible plan
- Re-estimate when significant new information emerges (scope change, team change, dependency change)
