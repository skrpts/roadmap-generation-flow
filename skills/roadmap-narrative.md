---
type: skill
id: roadmap-narrative
title: Roadmap Narrative
description: "Weaving strategic themes, initiatives, dependencies, timelines, and resource allocations into a compelling stakeholder-ready roadmap narrative"
tags: [Production, Planning, Communication]
connections:
  - target: llm-service
    type: runs_on
metadata:
  estimated_duration: "5-10 minutes"
  avg_tokens: 4000
  trigger: manual
---

## Roadmap Narrative

This skill turns structured roadmap data into a story stakeholders can understand, believe, and support. A roadmap is not a Gantt chart; it is an argument for where the product is going and why, and this skill makes that strategic logic visible.

### Core Capability

Given the themes, initiatives, dependency analysis, timeline, and resource allocation, this skill produces a continuous narrative covering strategic context, themes as chapters, key trade-offs, the execution plan, the resource reality, confidence and risks, and a twelve-month vision.

### Method

1. **Ground the reader:** Open with where the product stands today and restate the vision, connecting it to the themes that follow.
2. **Make choices visible:** Present each theme's rationale and surface the trade-offs — what was prioritised, deferred, and why.
3. **Be honest:** State the resource reality, confidence levels, and top risks directly rather than papering over constraints or contradictions.

### Output Structure

A single continuous narrative of 1,200-2,000 words with clear section headings, written for a mixed executive and cross-functional audience. The narrative feeds the assembly stage as the opening section of the roadmap document.
