---
type: source
id: roadmap-methodology-guide
title: Roadmap Methodology Guide
description: "Reference guide to product roadmap methodologies including NOW-NEXT-LATER, timeline-based, outcome-based, and theme-based approaches"
tags: [Production, Planning, Research]
connections:
  - target: theme-extraction
    type: references
metadata:
  trigger: manual
---

## Roadmap Methodology Guide

This reference guide covers the major product roadmap methodologies. The roadmap generation pipeline primarily uses a **theme-based, time-bound** approach, but understanding the alternatives helps product managers choose the right format for their context and adapt the pipeline outputs to different organisational needs.

### Methodology Comparison

| Methodology | Best For | Time Granularity | Commitment Level | Primary Audience |
|---|---|---|---|---|
| NOW-NEXT-LATER | Agile teams, high uncertainty | None (priority buckets) | Low — directional only | Internal teams |
| Timeline-based | Enterprise, waterfall-adjacent | Month/quarter specific | High — date commitments | Executives, sales, customers |
| Outcome-based | OKR-driven organisations | Quarterly | Medium — outcome commitments | Leadership, product teams |
| Theme-based | Strategic planning, portfolio | Quarterly | Medium — theme investment | Executives, board |
| Opportunity Solution Tree | Continuous discovery teams | None | Low — experiment-driven | Product teams |

### NOW-NEXT-LATER

**Concept:** Instead of committing to dates, organise initiatives into three buckets based on priority and readiness:

- **NOW:** Actively in progress or about to start. High confidence, well-understood, committed.
- **NEXT:** Coming soon. Good understanding of the problem, solution direction identified, but not yet committed.
- **LATER:** On the radar. Problem identified, but solution and timing are uncertain.

**Strengths:** Avoids false precision in timelines. Communicates priority without date pressure. Easy to update as priorities shift.

**Weaknesses:** Difficult for sales teams who need delivery dates. Can feel vague to executives accustomed to Gantt charts. Does not address resource allocation.

**When to use:** Early-stage products, rapidly changing markets, teams with less than 6 months of delivery data.

### Timeline-Based Roadmaps

**Concept:** Map initiatives to specific dates or date ranges on a timeline. Typically presented as a Gantt chart or swim-lane diagram.

**Strengths:** Clear and specific. Easy for non-product stakeholders to understand. Enables sales to make delivery commitments. Forces resource planning.

**Weaknesses:** Creates false precision — dates are estimates, not commitments, but stakeholders treat them as promises. Expensive to maintain as plans change. Encourages feature-factory thinking over outcome thinking.

**When to use:** Regulated industries with compliance deadlines. Enterprise products where customers have implementation timelines. Organisations where leadership requires date-specific plans.

**Risk mitigation:** If using timeline-based roadmaps, present dates as ranges (Q2 vs. "March 15th") and clearly label confidence levels.

### Outcome-Based Roadmaps

**Concept:** Instead of listing features, list the outcomes the product aims to achieve. Features are the tactics used to pursue outcomes, not the roadmap items themselves.

**Example:** Instead of "Build recommendation engine," the roadmap item is "Increase content discovery rate from 12% to 25%." The recommendation engine is one possible solution, evaluated alongside alternatives.

**Strengths:** Focuses the team on impact, not output. Creates space for experimentation — the team can pursue the best path to the outcome. Aligns naturally with OKR frameworks.

**Weaknesses:** Harder to communicate to non-product stakeholders ("what are you actually building?"). Requires strong discovery capabilities. Can feel abstract without concrete initiative detail.

**When to use:** Outcome-driven cultures. Teams with strong discovery practices. Product-led growth organisations.

### Theme-Based Roadmaps (This Pipeline's Primary Approach)

**Concept:** Organise the roadmap around strategic themes — areas of investment that connect to the product vision and business strategy. Initiatives are grouped under themes, making the strategic logic visible.

**Strengths:** Communicates strategy, not just features. Makes trade-offs visible (themes have relative investment levels). Supports portfolio-level discussions. Adapts well to both quarterly and annual planning.

**Weaknesses:** Themes can become too abstract if not grounded in concrete initiatives. Requires discipline to keep themes distinct and actionable.

**Best practices:**
- 4-7 themes per planning period (fewer is better)
- Each theme has a clear strategic rationale and measurable outcome
- Themes are balanced across customer value, platform health, and business growth
- Initiatives within themes are concrete and time-bound

### Opportunity Solution Tree (OST)

**Concept:** Developed by Teresa Torres. Structures product discovery as a tree: desired outcome → opportunities (customer needs) → solutions (ideas) → experiments (validation).

**Strengths:** Tightly couples discovery and delivery. Forces validation before commitment. Makes the reasoning chain from outcome to solution visible.

**Weaknesses:** Not a roadmap in the traditional sense — it is a discovery framework. Does not address resource allocation or timeline. Can be difficult to communicate to non-product audiences.

**When to use:** Continuous discovery teams. Products where the biggest risk is building the wrong thing (desirability risk > feasibility risk).

### Hybrid Approaches

Most mature product organisations use a hybrid:

- **Strategic level:** Theme-based or outcome-based (annual or semi-annual)
- **Tactical level:** Timeline-based or NOW-NEXT-LATER (quarterly)
- **Discovery level:** OST or similar (continuous)

This pipeline produces a **theme-based roadmap with timeline-bound initiatives** — a hybrid that provides strategic framing (themes) with tactical specificity (quarterly initiative plans).

### Choosing the Right Methodology

| If your organisation... | Consider... |
|---|---|
| Has strong OKR discipline | Outcome-based with theme overlay |
| Needs customer-facing commitments | Timeline-based with confidence levels |
| Is early-stage or highly uncertain | NOW-NEXT-LATER |
| Has portfolio-level planning needs | Theme-based |
| Has strong discovery practices | OST for discovery, theme-based for communication |

### Further Reading

- **"Inspired" by Marty Cagan** — Product strategy and roadmapping philosophy
- **"Continuous Discovery Habits" by Teresa Torres** — Opportunity Solution Trees and continuous discovery
- **"Escaping the Build Trap" by Melissa Perri** — Outcome-focused product management
- **"Good Strategy Bad Strategy" by Richard Rumelt** — Strategic thinking foundations
- **Janna Bastow's NOW-NEXT-LATER framework** — ProdPad blog and conference talks
