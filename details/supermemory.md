## Overview

Supermemory introduced a breakthrough technique called ASMR (Agentic Search and Memory Retrieval), which achieved approximately 99% on LongMemEval_s, published on March 22, 2026. This result put them ahead of every publicly benchmarked memory system.

## How ASMR Works

**Architecture:**
The system deploys an agent orchestrator utilizing 3 parallel reader (observer) agents powered by Gemini 2.0 Flash, which read through raw sessions concurrently. Their goal is targeted knowledge extraction across six vectors: Personal Information, Preferences, Events, Temporal Data, Updates, and Assistant Info.

**Retrieval Approach:**
When a question arrives, the system does not query a vector database but instead deploys 3 parallel search agents. These agents actively read and reason over stored findings, with specialized focuses: Agent 1 searches for direct facts and explicit statements, while Agent 2 looks for related context, social cues, and implications.

## Why It Matters

LongMemEval is designed to simulate real production environments with 115k+ token conversation histories, contradictory information, events spread across multiple sessions, and questions requiring temporal reasoning.

## Availability

Supermemory planned to publish and open source everything about this new agent memory system beginning of April 2026.

## Pricing

Open-source project.