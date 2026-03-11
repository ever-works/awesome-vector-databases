## Overview

Zep is an end-to-end context engineering platform designed specifically for AI agents. It solves the agent context problem by assembling comprehensive, relationship-aware context from multiple data sources with sub-200ms latency.

## Architecture

Zep uses Graphiti, a bi-temporal graph engine that stores both event time and ingestion time. This temporal knowledge graph tracks how facts change over time and maintains historical relationships between entities.

### Core Component: Graphiti

Graphiti is a temporally-aware knowledge graph engine that:
- Dynamically synthesizes unstructured conversational data and structured business data
- Maintains historical relationships across all data sources
- Tracks when facts were true, not just what facts exist
- Provides relationship-aware context blocks optimized for LLMs

## Key Features

- **Temporal Knowledge Graph**: Bi-temporal model tracking event time and ingestion time
- **Multi-Source Integration**: Combines chat history, business data, documents, and app events
- **Hybrid Search**: Combines graph-based memory with vector search
- **Sub-200ms Latency**: Fast context retrieval for real-time applications
- **Automatic Relationship Extraction**: Dynamically identifies and maintains entity relationships
- **Historical Context**: Understands how context evolves over time

## Performance

In the Deep Memory Retrieval (DMR) benchmark established by the MemGPT team, Zep achieves 94.8% accuracy compared to MemGPT's 93.4%, demonstrating superior performance in agent memory tasks.

## Integration

Zep integrates with:
- LangChain
- LlamaIndex
- Custom AI agent frameworks
- Various LLM providers (OpenAI, Anthropic, etc.)

## Use Cases

- Long-term memory for AI agents
- Customer support chatbots with conversation history
- Enterprise AI systems requiring relationship modeling
- Temporal reasoning applications
- Context-aware recommendation systems

## Pricing

Zep offers both cloud-hosted and self-hosted options with tiered pricing based on usage.