---
type: document
id: roadmap-communication-guide
title: Roadmap Communication Guide
description: "Guide to communicating product roadmaps effectively to different audiences — executives, teams, customers, and partners"
tags: [Production, planning:product, communication:stakeholder]
connections:
  - target: roadmap-narrative-writer
    type: references
metadata:
  trigger: manual
---

## Roadmap Communication Guide

The same roadmap must be communicated differently to different audiences. An executive wants strategic framing and risk awareness. An engineer wants feasibility and sequencing detail. A customer wants delivery commitments and value narrative. This guide covers how to adapt roadmap communication for each audience without compromising accuracy or trust.

### Core Principle: One Roadmap, Many Views

Maintain a single source of truth for the roadmap, but present different views of it to different audiences. Never create separate, contradictory roadmaps for different groups — this always ends badly when the versions are compared.

### Audience Profiles

#### Executives and Board Members

**What they care about:** Strategic direction, market positioning, risk, resource efficiency, financial impact.

**What they do not care about:** Technical implementation detail, individual initiative scope, sprint-level planning.

**Format:** 2-3 page written summary with a visual timeline. Quarterly updates.

**Communication principles:**
- Lead with strategic context — why this roadmap, why now
- Present themes, not features. "We are investing in enterprise readiness" not "We are building SSO, SCIM provisioning, and audit logging"
- Highlight trade-offs explicitly — executives respect honesty about what is not being done
- Include a confidence assessment — executives make better decisions when they understand the risk profile
- Connect to metrics — what is the expected impact on the numbers they track?
- Keep it to 10-15 minutes of reading time maximum

**Common mistakes:**
- Presenting a feature list disguised as strategy
- Avoiding discussion of risks or constraints
- Promising dates without confidence levels
- Using technical jargon that requires translation

#### Engineering and Design Teams

**What they care about:** Feasibility, sequencing, technical dependencies, team allocation, scope clarity.

**What they do not care about:** Market positioning narrative, board-level financial framing.

**Format:** Detailed initiative cards with dependency maps. All-hands presentation plus written document.

**Communication principles:**
- Be specific about scope — "what is in" and "what is out" for each initiative
- Show the dependency graph — engineers need to understand what blocks what
- Explain the sequencing rationale — why this initiative before that one
- Present resource allocation transparently — who is working on what, and is the plan realistic?
- Acknowledge technical debt and platform investment — teams lose trust when every initiative is customer-facing and no time is allocated for engineering health
- Invite pushback — if engineers say the timeline is unrealistic, listen

**Common mistakes:**
- Presenting timelines without explaining the assumptions
- Ignoring tech debt and expecting the team to absorb it silently
- Over-committing the team and calling it "ambitious"
- Not explaining why certain initiatives were prioritised over the team's preferred projects

#### Sales and Customer Success Teams

**What they care about:** What is shipping when. Which customer problems are being addressed. What they can promise to customers.

**What they do not care about:** Internal trade-offs, resource allocation, technical architecture.

**Format:** Feature-oriented slide deck with approximate timelines. FAQ document for common customer questions.

**Communication principles:**
- Frame in terms of customer value, not internal themes. "Customers will be able to export reports in any format" not "Data portability theme, Q3"
- Provide clear guidance on what can and cannot be promised to customers
- Use confidence levels to set expectations: "High-confidence Q3 delivery" vs. "Targeting Q4, subject to change"
- Include a "frequently asked by customers" section with prepared responses
- Update when plans change — stale commitments to customers are relationship poison

**Common mistakes:**
- Sharing internal timelines directly with customers without confidence disclaimers
- Promising features that are classified as "bets" (may not ship)
- Not updating sales when the roadmap changes
- Sharing the roadmap as a PDF that becomes instantly stale

#### Customers and External Partners

**What they care about:** Value delivery. When will their problems be solved? What is the product's direction?

**What they do not care about:** Internal team structure, resource constraints, technical dependencies.

**Format:** Public blog post, changelog, or customer advisory board presentation. Quarterly or semi-annually.

**Communication principles:**
- Frame everything in terms of outcomes and value — what customers will be able to do
- Use broad timeframes, not specific dates. "First half of 2026" not "March 15th"
- Only share high-confidence items externally — never share bets as commitments
- Be honest about direction without over-committing. "We are exploring X" is acceptable; "X is coming in Q3" is a commitment
- Provide context for prioritisation — customers are more accepting of delays when they understand the reasoning

**Common mistakes:**
- Sharing the internal roadmap directly (exposes competitive information, creates false expectations)
- Committing to features publicly before internal confidence is high
- Not following up when plans change
- Using internal jargon that customers do not understand

### Communication Formats

#### Written Summary (Executive View)

Structure:
1. Strategic context (2-3 paragraphs)
2. Theme overview with one-line descriptions
3. Key milestones by quarter (table format)
4. Risk and confidence assessment
5. Resource summary

Length: 2-3 pages.

#### Slide Deck (All-Hands or Customer View)

Structure:
1. Where we are today (metrics, achievements)
2. Where we are going (vision, themes)
3. How we get there (quarterly initiative highlights)
4. What to watch (risks, dependencies)
5. Q&A

Slides: 10-15 maximum. One idea per slide.

#### Initiative Cards (Engineering View)

Structure per initiative:
- Problem statement
- Scope (in / out)
- Success metrics
- Dependencies (blocking and soft)
- Team assignment
- Timeline with confidence level
- Risks and mitigations

#### Changelog / Blog Post (Customer View)

Structure:
1. What we shipped recently (celebrate wins)
2. What we are working on now (high confidence, in progress)
3. What is coming next (directional, not committed)
4. What we are exploring (experimental, no commitment)

### Handling Difficult Conversations

**"When will feature X ship?"**
→ Respond with confidence level. "Feature X is targeted for Q3 with high confidence" or "Feature X is on our radar but not yet scheduled — we are evaluating it for H2."

**"Why did you deprioritise my request?"**
→ Explain the trade-off. "We chose to invest in Y instead because it serves a broader set of customers. Your request is on our backlog and we are tracking demand."

**"Your competitor already has this."**
→ Acknowledge and redirect. "We are aware. We have chosen to differentiate on Z rather than match feature-for-feature. Here is why we believe that is the right strategy."

**"The roadmap changed — you promised this."**
→ Acknowledge the change, explain why, and offer alternatives. Never deny the change or blame the customer for misunderstanding.

### Version Control

- Number each roadmap version (v1.0, v1.1, v2.0)
- Track changes between versions with a brief changelog
- Archive previous versions for reference
- When communicating changes, reference the specific version that changed
