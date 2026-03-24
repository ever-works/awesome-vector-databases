## Overview

ASMR (Agentic Search and Memory Retrieval) is a breakthrough technique developed by Supermemory that uses multi-agent orchestration instead of traditional vector database retrieval.

## Architecture

### Parallel Reader Agents
The system deploys an agent orchestrator utilizing 3 parallel reader (observer) agents powered by Gemini 2.0 Flash, which read through raw sessions concurrently. Their goal is targeted knowledge extraction across six vectors:
- Personal Information
- Preferences
- Events
- Temporal Data
- Updates
- Assistant Info

### Parallel Search Agents
When a question arrives, the system does not query a vector database but instead deploys 3 parallel search agents:
- Agent 1: Searches for direct facts and explicit statements
- Agent 2: Looks for related context, social cues, and implications
- Agent 3: Provides additional perspectives

## Performance

ASMR achieved approximately 99% on LongMemEval_s, published on March 22, 2026, putting it ahead of every publicly benchmarked memory system.

## Why It Works

By using agents that actively read and reason over stored findings rather than relying on semantic similarity alone, ASMR better handles:
- Contradictory information
- Temporal reasoning
- Multi-session context
- Complex queries requiring synthesis

## Pricing

Planned for open-source release in April 2026.