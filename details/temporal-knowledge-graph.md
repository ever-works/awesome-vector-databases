## Overview

Temporal Knowledge Graphs extend traditional knowledge graphs by tracking how facts change over time, with each fact having explicit time metadata showing its validity period.

## Key Features

- Facts have validity windows (start time, end time)
- Historical relationships are preserved
- Temporal queries supported
- Evolution of knowledge tracked
- Time-aware reasoning enabled

## Graphiti Implementation

Zep AI's Graphiti is a temporally-aware knowledge graph engine where every fact carries explicit time metadata. When an agent records an episode, Graphiti decomposes it into entities (nodes), relationships (edges), and temporal attributes.

## Benefits for Agent Memory

- Track changing relationships ("Alice was project lead until January")
- Answer temporal queries ("Who managed the project in Q4?")
- Detect contradictions and updates
- Maintain historical context
- Support time-based reasoning

## Performance

On LongMemEval benchmark, systems using temporal knowledge graphs like Graphiti achieved 63.8% with GPT-4o, showing strong improvements in temporal reasoning.

## Use Cases

- AI agent memory systems
- CRM with relationship history
- Compliance tracking
- Medical records
- Project management

## Pricing

Concept/architecture, Graphiti open-source.