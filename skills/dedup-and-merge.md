---
type: skill
id: dedup-and-merge
title: Dedup and Merge
description: "Identifies duplicate or overlapping items in a collection and merges them into canonical entries"
tags: [Production, Quality, Data]
connections:
  - target: llm-service
    type: runs_on
---

## Capability

Scans a collection of items (research findings, feature requests, user feedback, literature references, roadmap items) for duplicates and near-duplicates. Groups related items together and produces a merged, deduplicated list with consolidated content.

## When to Use

- After collecting input from multiple sources that may overlap (e.g. user research interviews, literature searches, feature request backlogs)
- When assembling a roadmap from multiple stakeholder inputs
- Before synthesis stages that would be confused by duplicate entries
- After import or aggregation steps that combine data from different origins

## What It Does

1. **Exact duplicates** — identifies and removes items that are identical or near-identical in content
2. **Semantic duplicates** — identifies items that say the same thing in different words
3. **Partial overlaps** — identifies items that share significant content but also contain unique elements
4. **Merge** — for each group of duplicates, produces a single canonical entry that preserves all unique information from the group
5. **Provenance** — tracks which original items contributed to each merged entry

## What It Does NOT Do

- Judge which duplicate is "better" (it merges, preserving all unique content)
- Remove intentional repetition (e.g. recurring themes in a report)
- Modify content beyond deduplication (no editing, polishing, or restructuring)

## Inputs

A collection of items to deduplicate. Each item should be a discrete unit (a finding, a reference, a feature request, a paragraph).

## Outputs

A deduplicated list with merged entries. Each entry includes the consolidated content and a list of source items that were merged into it.
