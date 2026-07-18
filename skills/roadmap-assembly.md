---
type: skill
id: roadmap-assembly
title: Roadmap Assembly
description: "Assembling the narrative, themes, initiatives, dependencies, timeline, and resource plan into a single complete, consistent, stakeholder-ready roadmap document"
tags: [Production, Planning, Communication]
connections:
  - target: llm-service
    type: runs_on
metadata:
  estimated_duration: "5-8 minutes"
  avg_tokens: 5000
  trigger: manual
---

## Roadmap Assembly

This skill produces the final deliverable of the workflow: a single, coherent, professional roadmap document assembled from every upstream stage. This is not creative writing — the content already exists; the task is to structure it, enforce consistency, and produce something ready for stakeholder distribution.

### Core Capability

Given the roadmap narrative, strategic themes, initiative cards, dependency analysis, timeline, and resource allocation summary, this skill assembles a numbered document — executive summary, strategic narrative, theme overview, initiative plan, dependency map, timeline, resource allocation, detailed initiative cards, governance, and appendices.

### Method

1. **Assemble in order:** Place each upstream artifact into its section, leading with a stand-alone executive summary and the strategic narrative.
2. **Enforce consistency:** Verify initiative counts, quarters, team assignments, dependency references, and metrics match across all sections.
3. **Flag, do not resolve:** Where stages contradict one another, surface the inconsistency in the document rather than silently reconciling it.

### Output Structure

A single professional document with clear section numbering and a table of contents, typically 3,000-6,000 words. This is the workflow's final content artifact, handed to the language-polish stage for a final pass.
