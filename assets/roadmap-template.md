---
type: asset
id: roadmap-template
title: Roadmap Template
description: "Master template for the final roadmap document, providing the structure and placeholder sections for assembly"
tags: [Production, planning:product, communication:stakeholder]
connections:
  - target: roadmap-assembler
    type: references
metadata:
  trigger: manual
---

## Roadmap Document Template

Use this template as the structural foundation for the assembled roadmap document. Fill each section with the outputs from the corresponding pipeline stage.

---

# Product Roadmap — {{product_name}}

**Planning Horizon:** {{planning_horizon}}
**Version:** {{version}}
**Date:** {{date}}
**Owner:** {{product_owner}}
**Status:** Draft / Under Review / Approved

---

## Table of Contents

1. Executive Summary
2. Strategic Narrative
3. Theme Overview
4. Initiative Plan
5. Dependency Map
6. Timeline
7. Resource Allocation
8. Detailed Initiative Cards
9. Governance
10. Appendices

---

## 1. Executive Summary

*200-300 words. Must stand alone — a reader who only reads this section should understand the roadmap's key elements.*

**Planning period:** {{planning_horizon}}

**Strategic themes ({{theme_count}}):**
- {{theme_1_name}}: {{theme_1_one_liner}}
- {{theme_2_name}}: {{theme_2_one_liner}}
- {{theme_3_name}}: {{theme_3_one_liner}}
- *(continue for all themes)*

**Total initiatives:** {{initiative_count}}

**Key highlights:**
- {{highlight_1}}
- {{highlight_2}}
- {{highlight_3}}

**Resource position:** {{resource_summary}}

**Top risks:**
1. {{risk_1}}
2. {{risk_2}}
3. {{risk_3}}

**Twelve-month outcome:** {{vision_outcome}}

---

## 2. Strategic Narrative

*Insert the full output from the Roadmap Narrative Writer stage.*

{{roadmap_narrative}}

---

## 3. Theme Overview

### Summary Table

| # | Theme | Classification | Initiatives | Est. Effort (pw) | Key Metric | Quarter Focus |
|---|-------|---------------|-------------|-------------------|------------|---------------|
| 1 | {{theme_name}} | {{classification}} | {{count}} | {{effort}} | {{metric}} | {{quarters}} |

### Theme Descriptions

#### Theme 1: {{theme_1_name}}

**Classification:** {{table_stakes / differentiator / bet}}
**Strategic rationale:** {{why_this_theme_matters}}
**Key initiatives:** {{initiative_list}}
**Success metric:** {{metric}}
**What we are not doing:** {{deliberate_exclusions}}

*(Repeat for each theme)*

---

## 4. Initiative Plan

### By Theme

#### {{theme_name}}

| Initiative | Quarter | Effort (pw) | Confidence | Classification | Primary Team |
|---|---|---|---|---|---|
| {{initiative_name}} | {{quarter}} | {{effort}} | {{confidence}} | {{classification}} | {{team}} |

### Cross-Theme Notes

{{notes_on_initiatives_spanning_themes_or_excluded_initiatives}}

---

## 5. Dependency Map

### Dependency Matrix

| | {{init_A}} | {{init_B}} | {{init_C}} | {{init_D}} |
|---|---|---|---|---|
| **{{init_A}}** | — | {{dependency_type}} | — | — |
| **{{init_B}}** | — | — | {{dependency_type}} | — |

*Read as: row depends on column.*

### Critical Path

{{critical_path_narrative}}

**Critical path duration:** {{duration}}
**Highest-risk node:** {{node}} — {{risk_description}}

### Top Dependency Risks

| Risk | Initiatives Affected | Probability | Impact | Mitigation |
|---|---|---|---|---|
| {{risk}} | {{initiatives}} | {{probability}} | {{impact}} | {{mitigation}} |

---

## 6. Timeline

### Quarter-by-Quarter Plan

#### {{quarter_name}} (e.g., Q2 2026)

**Starting:**
- {{initiative}} ({{team}}, {{effort}})

**In Progress:**
- {{initiative}} ({{team}}, {{status}})

**Completing:**
- {{initiative}} ({{team}}, {{milestone}})

**Key Milestones:**
- {{milestone_date}}: {{milestone_description}}

**Decision Points:**
- {{decision_description}}

**Capacity Utilisation:**

| Team | Available (pw) | Committed (pw) | Utilisation | Status |
|---|---|---|---|---|
| {{team}} | {{available}} | {{committed}} | {{percentage}} | {{green/amber/red}} |

*(Repeat for each quarter)*

---

## 7. Resource Allocation

### Team Utilisation Summary

| Team | Q1 | Q2 | Q3 | Q4 | Annual Avg |
|---|---|---|---|---|---|
| {{team}} | {{utilisation}}% | {{utilisation}}% | {{utilisation}}% | {{utilisation}}% | {{avg}}% |

*Target: 70-85%. Green < 75%, Amber 75-85%, Red > 85%.*

### Capacity Conflicts

{{conflict_description_and_resolution}}

### Gap Analysis

| Gap Type | Description | Impact | Recommendation | Timeline |
|---|---|---|---|---|
| {{skill_gap / headcount / key_person}} | {{description}} | {{impact}} | {{recommendation}} | {{timeline}} |

---

## 8. Detailed Initiative Cards

### {{initiative_name}}

**Theme:** {{theme}}
**Quarter:** {{quarter}}
**Classification:** {{table_stakes / differentiator / bet}}
**Confidence:** {{high / medium / low}}
**Primary Team:** {{team}}
**Effort:** {{person_weeks}} person-weeks

**Problem:** {{problem_statement}}

**Outcome:** {{what_done_looks_like}}

**Success Metrics:**
- {{metric_1}}
- {{metric_2}}

**Dependencies:**
- {{dependency_1}} ({{blocking / constraining}})
- {{dependency_2}}

**Risks:**
- {{risk_1}}
- {{risk_2}}

---

*(Repeat for each initiative)*

---

## 9. Governance

### Review Cadence

| Cadence | Meeting | Participants | Purpose |
|---|---|---|---|
| Weekly | Tactical check-in | PM, Eng Lead, Design Lead | Track initiative status |
| Monthly | Strategic review | Product + Eng Directors | Assess roadmap health, approve changes |
| Quarterly | Planning session | Leadership team | Set next quarter direction |

### Change Process

| Change Level | Examples | Authority | Process |
|---|---|---|---|
| Minor | Scope tweak, < 2 week shift | Product Manager | Inform stakeholders |
| Moderate | Initiative added/deferred | Product Director | Monthly review approval |
| Major | Theme change, > 20% plan change | VP Product | Quarterly review approval |

### Decision Authority

{{decision_authority_matrix}}

### Escalation Path

{{escalation_path_description}}

---

## 10. Appendices

### A. Assumptions Register

| # | Assumption | Impact if Wrong | Validated? |
|---|---|---|---|
| 1 | {{assumption}} | {{impact}} | {{yes / no / partially}} |

### B. Methodology Notes

- **Effort estimation:** {{methodology}}
- **Realism multipliers:** {{multiplier_description}}
- **Capacity factor:** {{factor}} ({{rationale}})

### C. Glossary

| Term | Definition |
|---|---|
| {{term}} | {{definition}} |

### D. Version History

| Version | Date | Author | Changes |
|---|---|---|---|
| {{version}} | {{date}} | {{author}} | {{change_summary}} |

---

*Generated using the Roadmap Generation Flow skrpt on the Skrptiq platform.*
