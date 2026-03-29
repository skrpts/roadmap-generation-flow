---
type: prompt
id: initiative-breakdown-prompt
title: Initiative Breakdown Prompt
description: "Break strategic roadmap themes into concrete, scoped initiatives with clear outcomes, strategic classification, and confidence levels"
tags: [Production, Planning, Communication]
connections:
  - target: theme-extraction
    type: derived_from
  - target: dependency-graph-generator
    type: uses
metadata:
  estimated_duration: "8-12 minutes"
  avg_tokens: 4000
  trigger: manual
---

## Initiative Breakdown Prompt

You are a senior product manager. Your task is to take a set of strategic roadmap themes and break each one down into concrete, scoped initiatives that can be planned, resourced, and delivered within a single quarter.

### Input

**Strategic themes (from Vision to Themes stage):**
{{steps.vision-to-themes-prompt.output}}

**Planning horizon:**
[Use a 12-month planning horizon unless otherwise specified]

**Known constraints (technical debt, regulatory deadlines, contractual commitments):**
{{input.existing_commitments}}

**Team composition and capabilities:**
{{input.team_capacity}}

**Current product state (what exists today):**
{{input.technical_context}}

### Instructions

#### For Each Theme

##### Step 1: Initiative Brainstorming

Generate 4-8 candidate initiatives that would advance this theme. Think broadly:

- What would move the primary metric for this theme?
- What customer problems would this theme address, and what are the simplest solutions?
- What foundational work is needed before user-facing features can be built?
- What quick wins could demonstrate progress within the first month?
- What ambitious bets could transform the product if successful?

##### Step 2: Scoping

For each candidate initiative, assess scope:

- Can it be delivered within a single quarter by a team of 2-5 people? If not, decompose further.
- Is the scope well-understood, or does it require a discovery phase first?
- Are there natural phase boundaries (MVP → V1 → V2) that would allow incremental delivery?

Remove or split any initiative that cannot be reasonably delivered in one quarter. If an initiative is genuinely multi-quarter, define only the first quarter's deliverable as the initiative and note the continuation.

##### Step 3: Initiative Definition

For each initiative that survives scoping, provide:

1. **Initiative name:** Clear, concise, action-oriented (e.g., "Launch self-service onboarding flow," "Migrate payments to new processor")
2. **Theme:** Which strategic theme this initiative belongs to
3. **Problem statement:** What user or business problem does this initiative address? (2-3 sentences)
4. **Outcome definition:** What does "done" look like? What is the tangible deliverable? (be specific — "users can do X" not "improve X")
5. **Success metrics:** 1-2 measurable indicators that this initiative has achieved its intended outcome
6. **Strategic classification:**
   - **Table stakes:** Must have to remain competitive; failure to deliver creates real risk
   - **Differentiator:** Creates meaningful competitive advantage; delivers unique value
   - **Bet:** Unvalidated hypothesis with high potential upside; acceptable to fail if learnings are captured
7. **Confidence level:**
   - **High:** Validated need, understood implementation, experienced team
   - **Medium:** Reasonable hypothesis, some technical unknowns, adequate team
   - **Low:** Speculative need, significant technical unknowns, or skill gaps
8. **Estimated effort:** T-shirt size (S: 1-2 weeks, M: 3-6 weeks, L: 7-12 weeks, XL: 13+ weeks)
9. **Target quarter:** When this initiative should be delivered
10. **Customer segment:** Which user segments benefit most
11. **Prerequisites:** What must be true or done before this initiative can start
12. **Risks:** 1-2 key risks that could derail this initiative

##### Step 4: Theme Validation

After defining initiatives for all themes, validate:

- **Coverage:** Does each theme have at least 3 initiatives? If not, the theme may be too narrow — consider merging it.
- **Overload:** Does any theme have more than 8 initiatives? If so, it may be too broad — consider splitting.
- **Balance:** Is the mix of table stakes, differentiators, and bets appropriate? A roadmap with only table stakes is reactive; one with only bets is reckless. Aim for roughly 40% table stakes, 40% differentiators, 20% bets.
- **Feasibility:** Is the total effort across all initiatives plausible given the team's capacity? If total effort exceeds capacity by more than 30%, the roadmap needs trimming before proceeding to dependency mapping.

### Output Format

Present the initiatives in two formats:

**1. Summary table:**

| Theme | Initiative | Classification | Confidence | Effort | Quarter |
|-------|-----------|---------------|------------|--------|---------|
| ... | ... | ... | ... | ... | ... |

**2. Detailed initiative cards:**

For each initiative, a card containing all 12 elements defined in Step 3.

**3. Theme health check:**

For each theme, note:
- Total initiative count
- Classification mix (table stakes / differentiator / bet)
- Confidence distribution (high / medium / low)
- Total estimated effort
- Any gaps or concerns

### Constraints

- Every initiative must be deliverable within a single quarter. Multi-quarter work must be broken into quarterly milestones.
- Do not create "research" or "discovery" initiatives unless they have a concrete deliverable (a decision document, a prototype, a validated hypothesis). Discovery without a deliverable is not an initiative.
- Each initiative must have at least one measurable success metric. "Improve user experience" is not a metric; "reduce time-to-first-value from 15 minutes to 5 minutes" is.
- Do not pad the initiative list with trivial items to make a theme look busy. Fewer, meaningful initiatives are better than many shallow ones.
- If the input themes are vague or insufficiently defined, return clarifying questions rather than guessing at initiatives.
