## Overview

EmbeddixDB is a vector database optimized for AI applications, featuring both MCP server for AI assistants and REST API.

## Features

- MCP Server: Direct integration with Claude and other AI assistants via Model Context Protocol
- Vector Search: HNSW and flat indexes with 256x memory compression via quantization
- Flexible Storage: In-memory, BoltDB, or BadgerDB persistence backends
- Auto-Embedding: Automatic text-to-vector conversion with Ollama or ONNX models
- Advanced Analytics: Sentiment analysis, entity extraction, and topic modeling
- Real-time Operations: Live vector insertion, updates, and deletion
- High Performance: ~65,000 queries/sec on M1 MacBook Pro; on M4 Pro: ~25,374 queries/sec search, ~32,113 vectors/sec insert

Available MCP Tools:
- create_collection
- add_vectors
- search_vectors
- get_vector
- delete_vector
- list_collections
- delete_collection

REST API endpoints for collections, documents, search, with OpenAPI docs.

## Architecture

- MCP Server: Stdio-based implementing Model Context Protocol
- Vector Store: HNSW and flat indexes with quantization
- Persistence: Pluggable backends (Memory, BoltDB, BadgerDB)
- AI Integration: ONNX Runtime and Ollama for embeddings
- REST API: HTTP API with OpenAPI documentation

## Use Cases

- LLM Memory Storage: Store conversation history, user preferences
- RAG: Index documents and retrieve relevant chunks
- Tool Learning: Track successful tool usage patterns

## Pricing

Free and open-source under the MIT License.