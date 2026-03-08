## Overview

Langfuse is an open-source LLM engineering platform that helps teams collaboratively debug, analyze, and iterate on their LLM applications. Provides LLM Observability, metrics, evals, prompt management, playground, and datasets.

## Core Features

### LLM Observability
- Purpose-built for LLM applications with native understanding of LLM-specific concepts
- Captures token usage, model parameters, prompt/completion pairs, and evaluation scores
- Application tracing for every operation: LLM calls, retrieval steps, tool executions, and custom logic
- Timing, inputs, outputs, and metadata tracking

### Prompt Management
- Systematic approach to storing, versioning, and retrieving prompts
- Central management instead of hardcoding prompts in application code
- Version control for prompt iterations

### Vector Database Integration
- Monitors RAG pipelines that fetch relevant context from vector databases (ChromaDB, etc.)
- Tracks document retrieval operations
- Vector search monitoring (VectorStoreRetriever)
- Answer generation tracking

## OpenTelemetry Support

OTEL-native Langfuse SDK v3 is a thin layer on top of official OpenTelemetry client that:
- Automatically converts spans into rich Langfuse observations
- Provides first-class helpers for token usage and cost tracking
- Supports prompt linking and scoring

## Integrations

- OpenTelemetry
- LangChain
- OpenAI SDK
- LiteLLM
- ChromaDB and other vector databases