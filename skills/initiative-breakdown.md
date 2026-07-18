---
type: skill
id: initiative-breakdown
title: Initiative Breakdown
description: "Breaking strategic roadmap themes into concrete, scoped, single-quarter initiatives with clear outcomes, strategic classification, and confidence levels"
tags: [Production, Planning, Communication]
connections:
  - target: llm-service
    type: runs_on
metadata:
  estimated_duration: "8-12 minutes"
  avg_tokens: 4000
  trigger: manual
---

## Initiative Breakdown

This skill turns strategic themes into a concrete, deliverable initiative plan. Themes give a roadmap direction; initiatives give it substance — the specific, scoped pieces of work that a team can plan, resource, and ship within a single quarter.

### Core Capability

Given the strategic themes together with team capacity, technical context, and existing commitments, this skill decomposes each theme into 3-6 scoped initiatives, defines the outcome and success metrics for each, classifies its strategic role (table stakes, differentiator, or bet), and assigns a confidence level and target quarter.

### Method

1. **Brainstorm and scope:** Generate candidate initiatives per theme, then scope each to a single quarter — decomposing or splitting anything larger.
2. **Define:** For every surviving initiative capture name, problem, outcome, success metrics, classification, confidence, effort, quarter, segment, prerequisites, and risks.
3. **Validate themes:** Check coverage (≥3 initiatives per theme), balance of classifications, and total effort against capacity before the plan proceeds downstream.

### Output Structure

A summary table plus detailed initiative cards and a per-theme health check. The initiative plan feeds the dependency, timeline, resource, narrative, and assembly stages downstream.
