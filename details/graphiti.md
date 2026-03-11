## Overview

Graphiti is an open-source framework for building and querying temporally-aware knowledge graphs, specifically designed for AI agents operating in dynamic environments. It powers the core memory system in Zep's context engineering platform.

## Key Features

- **Temporal Awareness**: Tracks when facts were true with explicit validity intervals (t_valid, t_invalid)
- **Bi-Temporal Model**: Stores both event time (when something happened) and ingestion time (when it was recorded)
- **Dynamic Updates**: Continuously integrates user interactions and enterprise data without batch recomputation
- **Hybrid Search**: Combines semantic search, keyword matching, and graph traversal
- **Real-Time Processing**: Incrementally processes incoming data with instant entity and relationship updates
- **Low Latency**: Precise queries without LLM summarization overhead

## Architecture

Every graph edge (relationship) in Graphiti includes:
- Explicit validity intervals for temporal reasoning
- Relationship metadata and context
- Source attribution for traceability

The framework maintains communities of related entities that evolve over time.

## Integration

### Model Context Protocol (MCP)

Graphiti includes an MCP server, enabling integration with:
- Claude (Anthropic)
- Cursor IDE
- Other MCP-compatible clients

### Supported Backends

- Neo4j (primary graph database)
- OpenAI (embeddings and LLM)
- Azure OpenAI
- Google Gemini
- Anthropic Claude

## Performance

In the Deep Memory Retrieval (DMR) benchmark, Graphiti-powered systems achieve 94.8% accuracy versus 93.4% for MemGPT, demonstrating superior performance in memory retrieval tasks.

## Use Cases

- AI agent memory systems
- Conversational AI with historical context
- Enterprise knowledge management
- Temporal reasoning applications
- Dynamic relationship tracking
- Multi-source data integration

## Pricing

Free and open-source under the Apache 2.0 license.