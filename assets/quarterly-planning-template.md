---
type: asset
id: quarterly-planning-template
title: Quarterly Planning Template
description: "Template for quarterly planning breakdowns, mapping initiatives to teams, timelines, and capacity within a single quarter"
tags: [Production, Citations, Planning]
connections:
  - target: resource-mapper
    type: references
metadata:
  trigger: manual
---

## Quarterly Planning Template

Use this template to plan and track a single quarter's execution against the product roadmap. Complete one instance per quarter.

---

# Quarterly Plan — {{quarter_name}} (e.g., Q2 2026)

**Quarter dates:** {{start_date}} — {{end_date}}
**Planning owner:** {{product_manager}}
**Last updated:** {{date}}
**Status:** Planning / In Progress / Complete / Retrospective Done

---

## 1. Quarter Objectives

What does success look like at the end of this quarter?

| # | Objective | Key Result | Target | Current | Status |
|---|-----------|-----------|--------|---------|--------|
| 1 | {{objective}} | {{key_result}} | {{target_value}} | {{current_value}} | {{on_track / at_risk / off_track}} |
| 2 | {{objective}} | {{key_result}} | {{target_value}} | {{current_value}} | {{status}} |
| 3 | {{objective}} | {{key_result}} | {{target_value}} | {{current_value}} | {{status}} |

---

## 2. Initiative Commitments

### Committed (High Confidence)

These initiatives are staffed, scoped, and expected to be delivered this quarter.

| Initiative | Theme | Team | Start | End | Effort (pw) | Owner |
|---|---|---|---|---|---|---|
| {{name}} | {{theme}} | {{team}} | Wk {{n}} | Wk {{n}} | {{effort}} | {{owner}} |

### Stretch (Medium Confidence)

These initiatives are planned for this quarter but may slip to next quarter if higher-priority work expands.

| Initiative | Theme | Team | Effort (pw) | Condition for Starting |
|---|---|---|---|---|
| {{name}} | {{theme}} | {{team}} | {{effort}} | {{condition}} |

### Carry-Over from Previous Quarter

Initiatives that started last quarter and continue into this one.

| Initiative | Theme | Team | Remaining Effort (pw) | Expected Completion |
|---|---|---|---|---|
| {{name}} | {{theme}} | {{team}} | {{remaining}} | Wk {{n}} |

---

## 3. Team Capacity

### Capacity Calculation

| Team | Headcount | Weeks in Quarter | Gross Capacity (pw) | Absences (pw) | Operational Overhead (pw) | Net Available (pw) |
|---|---|---|---|---|---|---|
| {{team}} | {{headcount}} | {{weeks}} | {{gross}} | {{absences}} | {{overhead}} | {{net}} |

### Allocation vs. Capacity

| Team | Net Available (pw) | Committed (pw) | Stretch (pw) | Utilization (Committed) | Utilization (All) | Status |
|---|---|---|---|---|---|---|
| {{team}} | {{available}} | {{committed}} | {{stretch}} | {{pct}}% | {{pct}}% | {{green / amber / red}} |

**Guidelines:**
- Green: < 75% committed utilization (healthy buffer)
- Amber: 75-85% committed utilization (limited buffer)
- Red: > 85% committed utilization (no buffer for unplanned work)

---

## 4. Dependencies and Risks

### Internal Dependencies

| Dependent Initiative | Depends On | Type | Expected Resolution Date | Status |
|---|---|---|---|---|
| {{initiative}} | {{dependency}} | {{hard / soft}} | Wk {{n}} | {{resolved / on_track / at_risk}} |

### External Dependencies

| Initiative | External Dependency | Owner | Expected Date | Status | Mitigation if Delayed |
|---|---|---|---|---|---|
| {{initiative}} | {{dependency}} | {{external_party}} | {{date}} | {{status}} | {{mitigation}} |

### Top Risks

| Risk | Probability | Impact | Affected Initiatives | Mitigation | Owner |
|---|---|---|---|---|---|
| {{risk}} | {{high / medium / low}} | {{high / medium / low}} | {{initiatives}} | {{mitigation}} | {{owner}} |

---

## 5. Key Milestones

| Date | Milestone | Initiative | Significance |
|---|---|---|---|
| Wk {{n}} | {{milestone}} | {{initiative}} | {{why_it_matters}} |

---

## 6. Decision Points

Scheduled moments during the quarter where the team will assess progress and potentially adjust the plan.

| Date | Decision | Options | Decision Maker | Deadline for Decision |
|---|---|---|---|---|
| Wk {{n}} | {{decision_description}} | {{option_a}} / {{option_b}} | {{role}} | Wk {{n}} |

---

## 7. Weekly Status Tracker

| Week | Highlights | Blockers | Decisions Needed | Status |
|---|---|---|---|---|
| Wk 1 | | | | {{on_track / at_risk / blocked}} |
| Wk 2 | | | | |
| Wk 3 | | | | |
| Wk 4 | | | | |
| Wk 5 | | | | |
| Wk 6 | | | | |
| Wk 7 | | | | |
| Wk 8 | | | | |
| Wk 9 | | | | |
| Wk 10 | | | | |
| Wk 11 | | | | |
| Wk 12 | | | | |
| Wk 13 | | | | |

---

## 8. Quarter Retrospective

*Complete at the end of the quarter.*

### Delivery Summary

| Initiative | Planned | Delivered | On Time? | Notes |
|---|---|---|---|---|
| {{name}} | {{scope}} | {{actual}} | {{yes / no / partial}} | {{notes}} |

### Metrics Review

| Objective | Key Result | Target | Actual | Hit? |
|---|---|---|---|---|
| {{objective}} | {{key_result}} | {{target}} | {{actual}} | {{yes / no / partial}} |

### Learnings

**What went well:**
- {{learning}}

**What did not go well:**
- {{learning}}

**What to change next quarter:**
- {{action}}

### Velocity Calibration

**Planned effort:** {{planned_pw}} person-weeks
**Actual effort:** {{actual_pw}} person-weeks
**Velocity factor:** {{actual / planned}} (use this to calibrate next quarter's estimates)

---

*Generated using the Roadmap Generation Flow skrpt on the Skrptiq platform.*
