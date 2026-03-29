---
type: document
id: roadmap-governance-framework
title: Roadmap Governance Framework
description: "Framework for roadmap governance including review cadence, change management process, decision authority, and escalation paths"
tags: [Production, planning:product, communication:stakeholder]
connections:
  - target: roadmap-generation-flow
    type: references
metadata:
  trigger: manual
---

## Roadmap Governance Framework

A roadmap without governance is a snapshot that decays. This framework defines how the roadmap is maintained, updated, and communicated over its lifecycle. It covers review cadence, change management, decision authority, and escalation.

### Governance Principles

1. **The roadmap is a living document.** It is updated regularly to reflect new information, not treated as a fixed plan.
2. **Changes are transparent.** When the roadmap changes, stakeholders are informed of what changed, why, and what the impact is.
3. **Authority is clear.** Everyone knows who can approve changes and at what level.
4. **Trade-offs are explicit.** Adding to the roadmap requires removing or deferring something else, unless new resources are provided.

### Review Cadence

#### Weekly: Tactical Check-in (15-30 minutes)

**Participants:** Product manager, engineering lead, design lead
**Purpose:** Track execution against the current quarter's plan
**Agenda:**
- Initiative status updates (on track / at risk / blocked)
- Emerging blockers and proposed mitigations
- Resource issues (team member availability, skill gaps)
- Dependency status (are upstream dependencies on track?)

**Output:** Updated initiative status. Escalation of any issues that cannot be resolved within the team.

#### Monthly: Strategic Review (60 minutes)

**Participants:** Product director, product managers, engineering managers, design lead, data/analytics lead
**Purpose:** Assess roadmap health and make tactical adjustments
**Agenda:**
- Quarter progress against plan (% of initiatives on track, at risk, completed)
- Metric review: are the roadmap's target metrics moving in the right direction?
- Change requests: review any proposed additions, scope changes, or deferrals
- Resource reallocation: adjust team assignments if needed
- Risk review: assess top risks and update mitigations

**Output:** Approved changes (if any). Updated risk register. Communication to affected stakeholders.

#### Quarterly: Strategic Planning (Half-day)

**Participants:** Leadership team, product directors, engineering directors, finance
**Purpose:** Set direction for the next quarter and review the roadmap's strategic alignment
**Agenda:**
- Retrospective on the past quarter: what was delivered, what was not, what was learned
- OKR review: are the strategic objectives still correct?
- Theme assessment: are the roadmap themes still the right themes?
- Next quarter planning: which initiatives move forward, which are added, which are deferred
- Resource planning: is the team right-sized for the plan?
- Budget review: are costs on track?

**Output:** Approved next-quarter plan. Updated roadmap document. Stakeholder communication.

#### Annual: Strategic Reset (Full day)

**Participants:** Executive team, product leadership, engineering leadership
**Purpose:** Refresh the product vision, set annual OKRs, and establish the roadmap framework for the year
**Agenda:**
- Market and competitive review
- Customer insight synthesis
- Vision refresh
- Annual OKR setting
- Theme definition for the year
- Resource and budget planning

**Output:** Updated product vision. Annual OKRs. Roadmap themes for the year.

### Change Management Process

#### Change Categories

| Category | Examples | Authority | Process |
|---|---|---|---|
| **Minor** | Scope adjustment within an initiative, timeline shift < 2 weeks, team member swap | Product manager | Inform stakeholders, update status |
| **Moderate** | New initiative added, initiative deferred, timeline shift > 2 weeks, team reallocation | Product director | Monthly review approval, stakeholder communication |
| **Major** | Theme added or removed, >20% of quarterly plan changed, significant resource change | VP Product / Leadership | Quarterly review approval, broad stakeholder communication |
| **Emergency** | Production incident requiring roadmap pause, regulatory deadline change, key person departure | VP Product (immediate) | Immediate decision, retrospective review |

#### Change Request Template

For moderate and major changes:

1. **What is changing?** (initiative added/removed/modified, timeline shift, resource change)
2. **Why?** (new information, market change, customer feedback, technical discovery)
3. **What is the impact?** (which other initiatives are affected, timeline implications, resource implications)
4. **What is the trade-off?** (what is being deferred or descoped to accommodate this change)
5. **Who is affected?** (teams, stakeholders, customers)
6. **Recommendation:** (proposed course of action)

### Decision Authority Matrix

| Decision | Product Manager | Product Director | VP Product | CEO/Leadership |
|---|---|---|---|---|
| Adjust initiative scope (minor) | Decide | Inform | — | — |
| Add/defer initiative within theme | Recommend | Decide | Inform | — |
| Shift initiative between quarters | Recommend | Decide | Inform | — |
| Add/remove a strategic theme | — | Recommend | Decide | Inform |
| Change resource allocation across teams | Recommend | Recommend | Decide | Inform |
| Commit to external delivery date | — | Recommend | Decide | Approve |
| Cancel a committed initiative | — | Recommend | Decide | Inform |

### Escalation Path

When issues cannot be resolved at the current level:

1. **Product manager → Product director:** Initiative-level conflicts, resource constraints within a team, scope disagreements
2. **Product director → VP Product:** Cross-team resource conflicts, theme-level trade-offs, customer commitment risks
3. **VP Product → Leadership:** Strategic direction changes, budget implications, organisational restructuring

**Escalation expectations:**
- Escalate early, not late. A problem surfaced in week 2 is manageable; the same problem surfaced in week 10 is a crisis.
- Always escalate with a recommendation, not just a problem statement.
- Document escalations and their resolutions for retrospective learning.

### Communication Plan

| Audience | Format | Frequency | Content Level |
|---|---|---|---|
| Executive team | Written summary + dashboard | Monthly | Strategic: themes, metrics, risks |
| Product + engineering teams | All-hands presentation | Quarterly | Tactical: initiatives, timelines, assignments |
| Sales + customer success | Slide deck + FAQ | Quarterly | Customer-facing: what is shipping when |
| Individual contributors | Team-level updates | Weekly | Execution: sprint goals, blockers |
| Customers (if applicable) | Blog post or changelog | Quarterly | Outcomes: what is new, what is coming |

### Anti-Patterns to Avoid

- **Roadmap as contract:** Treating the roadmap as a binding commitment rather than a strategic plan. Dates are targets, not promises.
- **Silent changes:** Modifying the roadmap without informing stakeholders. This erodes trust.
- **Addition without subtraction:** Adding new initiatives without deferring or removing existing ones. This creates an infeasible plan.
- **Review theatre:** Holding review meetings that review status but never make decisions. Reviews must have decision authority.
- **Stakeholder veto loop:** Allowing any stakeholder to block changes indefinitely. Escalation paths exist for a reason.
- **Annual roadmap, annual update:** Creating the roadmap once a year and treating it as fixed. Markets change; the roadmap must change with them.
