---
type: service
id: claude-service
title: Claude Service
description: "Anthropic Claude integration for strategic analysis, narrative writing, and structured planning throughout the roadmap generation pipeline"
tags: [Production, Tested]
connections:
  - target: anthropic-claude
    type: depends_on
metadata:
  trigger: automatic
---

## Claude Service — Roadmap Generation

This skrpt uses Anthropic Claude as the primary AI service across all stages of the roadmap generation pipeline. Claude's strengths in structured reasoning, long-context synthesis, and nuanced writing make it well-suited for strategic product planning.

### Usage Across the Pipeline

#### Stage 1-2: Theme Extraction and Initiative Breakdown
- **Model:** Claude Sonnet or Opus
- **Context window usage:** High — requires processing vision documents, OKRs, customer feedback, and competitive analysis simultaneously
- **Key capability:** Pattern recognition across diverse inputs to identify convergent themes; structured decomposition of themes into scoped initiatives
- **Typical token usage:** 2,500-4,000 tokens per stage

#### Stage 3: Dependency Mapping
- **Model:** Claude Sonnet or Opus
- **Context window usage:** High — requires holding all initiatives in context simultaneously to assess pairwise dependencies
- **Key capability:** Systematic relationship analysis, critical path identification, risk assessment
- **Typical token usage:** 2,500-3,500 tokens

#### Stage 4-5: Timeline Calculation and Resource Mapping
- **Model:** Claude Sonnet
- **Context window usage:** Medium-High — requires initiative data, dependency graph, and team capacity data
- **Key capability:** Quantitative reasoning with realism multipliers, capacity modelling, conflict identification
- **Typical token usage:** 2,000-3,000 tokens per stage

#### Stage 6: Narrative Writing
- **Model:** Claude Opus (recommended for highest quality narrative)
- **Context window usage:** Very High — requires all previous stage outputs as context to produce a coherent narrative
- **Key capability:** Long-form strategic writing, audience adaptation, trade-off framing
- **Typical token usage:** 3,000-4,000 tokens

#### Stage 7: Document Assembly
- **Model:** Claude Sonnet or Opus
- **Context window usage:** Very High — assembles all outputs into a single document
- **Key capability:** Structured document assembly, consistency checking, formatting
- **Typical token usage:** 4,000-5,000 tokens

### Configuration Notes

- **Temperature:** Use low temperature (0.2-0.3) for analytical stages (dependency mapping, timeline calculation). Use moderate temperature (0.5-0.7) for narrative writing.
- **System prompt:** Each stage has a dedicated system prompt embedded in the prompt node. No additional system prompt is needed.
- **Streaming:** Recommended for narrative writing and document assembly stages to provide progressive feedback.
- **Total pipeline token usage:** Approximately 20,000-30,000 tokens for a full roadmap generation run.
