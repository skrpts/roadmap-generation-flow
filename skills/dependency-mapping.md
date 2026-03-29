---
type: skill
id: dependency-mapping
title: Dependency Mapping
description: "Mapping technical and business dependencies between product initiatives to identify critical paths, sequencing constraints, and risk concentrations"
tags: [Production, Tested, Planning, Communication]
connections:
  - target: llm-service
    type: runs_on
metadata:
  estimated_duration: "5-8 minutes"
  avg_tokens: 2500
  trigger: manual
---

## Dependency Mapping

This skill enables the systematic identification and analysis of dependencies between product initiatives. Dependencies are the hidden structure of a roadmap — they determine what can be done in parallel, what must be sequenced, and where delays in one area will cascade into others.

### Core Capabilities

#### Dependency Identification

For each pair of initiatives on the roadmap, assess whether a dependency exists. Dependencies are directional: "A depends on B" means A cannot be completed (or started) until B reaches a defined state.

**Sources of dependencies:**

1. **Technical dependencies:** Initiative A requires a technical capability that Initiative B provides
   - API dependencies: client feature needs a new API endpoint
   - Data dependencies: analytics feature needs a data pipeline
   - Infrastructure dependencies: feature requires a platform upgrade
   - Shared component dependencies: two features need the same redesigned component

2. **Business dependencies:** Initiative A's value proposition depends on Initiative B's success
   - Feature bundling: premium tier only makes sense if free tier drives adoption
   - Sequential value: onboarding improvements only matter if acquisition is successful
   - Market timing: localisation only matters if market entry strategy is approved

3. **Resource dependencies:** Initiatives A and B require the same team, specialist, or resource
   - Same team: both initiatives need the payments team, which can only work on one at a time
   - Specialist bottleneck: both need the single machine learning engineer
   - Shared infrastructure: both need access to the staging environment during testing

4. **Knowledge dependencies:** Initiative A requires learnings from Initiative B
   - Experiment dependencies: the approach for A depends on the results of B's A/B test
   - Research dependencies: A's design depends on the findings of B's user research
   - Validation dependencies: A's business case depends on B demonstrating market demand

#### Dependency Classification

For each identified dependency, classify its strength:

- **Hard dependency:** A literally cannot proceed without B. Violating this dependency produces a broken product, a failed deployment, or a meaningless feature. Example: the mobile app cannot display user profiles until the profiles API exists.

- **Soft dependency:** A can proceed without B, but with reduced quality, increased effort, or partial functionality. Example: the reporting dashboard can launch without the data export feature, but users will need a workaround.

- **Preferential dependency:** A is better if B goes first, but neither depends on the other in a strict sense. Example: it is preferable to redesign the navigation before adding new feature sections, but not strictly necessary.

Only hard dependencies should constrain the timeline. Soft and preferential dependencies should inform sequencing preferences but not create bottlenecks.

#### Critical Path Analysis

The critical path is the longest chain of hard dependencies in the roadmap. It determines the minimum possible timeline for the complete roadmap, regardless of how many teams are working in parallel.

To identify the critical path:

1. Map all hard dependencies as a directed graph
2. Calculate the total duration of each dependency chain (summing the effort estimates of each initiative in the chain)
3. The chain with the longest total duration is the critical path
4. Any delay to any initiative on the critical path delays the entire roadmap

Initiatives on the critical path deserve:
- Higher confidence in their estimates (apply larger buffers if uncertainty is high)
- Priority access to resources and decision-making
- More frequent progress monitoring
- Contingency plans in case they are delayed

#### Dependency Risk Assessment

Dependencies create risk. Analyse the dependency graph for:

- **Fan-out risk:** An initiative with many dependents (others depend on it) is a single point of failure. If it is delayed, multiple initiatives are affected.
- **Fan-in risk:** An initiative with many dependencies (it depends on many others) is vulnerable to delays in any of its prerequisites.
- **Chain risk:** Long dependency chains (4+ initiatives) amplify delay — each link in the chain adds probability of slippage.
- **Circular dependencies:** A depends on B depends on A. These indicate a design problem — the initiatives need to be re-scoped to break the cycle.

### Output Standards

Dependency mapping output must include:

1. A **dependency matrix** — a table showing all pairwise dependencies with their type and strength
2. A **critical path narrative** — a description of the critical path, its total duration, and the key risks along it
3. A **dependency risk summary** — initiatives with the highest fan-out risk, fan-in risk, or chain risk
4. A **recommended sequencing** — a proposed order of execution that respects hard dependencies, optimises for soft dependencies, and maximises parallelism

### Constraints

- Only hard dependencies should block the timeline — do not treat preferences as constraints
- Always check for circular dependencies — they must be resolved before the roadmap can be finalised
- Update the dependency map whenever initiatives are added, removed, or re-scoped
- Dependencies between teams are often the most important and the most overlooked — explicitly probe for cross-team dependencies
