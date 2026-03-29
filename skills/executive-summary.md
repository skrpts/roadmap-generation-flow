---
type: skill
id: executive-summary
title: Executive Summary
description: "Distilling complex analysis into concise, decision-ready executive summaries for senior stakeholders"
tags: [Production, Tested]
connections:
  - target: llm-service
    type: runs_on
metadata:
  estimated_duration: "3 minutes"
  avg_tokens: 2500
  trigger: manual
---

## Executive Summary

This skill takes the output of a multi-stage analysis pipeline and distils it into a concise executive summary suitable for senior leadership. The summary enables decisions without requiring the reader to process the full analysis.

### Core Capability

Given detailed analysis outputs, this skill produces a structured executive summary that communicates the essential findings, recommendations, and required decisions in under two pages.

### Summary Structure

**1. Context (2-3 sentences)**
What was analysed and why. The reader should understand the scope and motivation without any prior context.

**2. Key Findings (3-5 bullet points)**
The most important discoveries from the analysis. Each finding must be:
- **Specific:** "Onboarding completion dropped 15% in Q3" not "Onboarding needs improvement"
- **Evidence-based:** Reference the supporting data, even briefly
- **Actionable:** Connect to a decision or action the reader can take

**3. Recommendations (numbered list)**
What the analysis suggests doing. Each recommendation must include:
- The recommended action
- The expected outcome
- The resources or investment required
- The risk of inaction

**4. Decision Required**
If the summary is driving a decision, state it explicitly:
- What decision is needed?
- What are the options?
- What is the recommended option and why?
- What is the deadline for the decision?

**5. Next Steps**
Concrete actions with owners and timelines. No vague "further investigation needed" without specifying what, by whom, and by when.

### Writing Principles

- **Lead with the conclusion.** Executives read the first paragraph. If they stop there, they should still know the answer.
- **Quantify everything possible.** "Revenue impact of £2.3M" not "significant revenue impact".
- **Acknowledge uncertainty.** If the data is incomplete, say so. A confident summary built on shaky data is worse than an honest one.
- **Use plain language.** Avoid jargon, acronyms without expansion, and technical detail that the audience does not need.
- **One page is better than two.** Every sentence must earn its place.

### Anti-Patterns

- **Burying the lead:** Starting with methodology or background instead of findings
- **Hedging everything:** "It might be possible that users could potentially prefer..." — commit to a position
- **Data dumping:** Including every finding rather than the important ones
- **Missing the "so what?":** Presenting findings without connecting them to actions or decisions
- **Passive voice:** "It was determined that..." — name the actor, state the finding directly

### Output Structure

The executive summary produces:
- A one-page summary document following the structure above
- A decision matrix (if applicable) with options, trade-offs, and a recommendation
- A next-steps table with actions, owners, and deadlines
