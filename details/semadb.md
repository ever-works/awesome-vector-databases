## Overview

SemaDB provides vector and hybrid search capabilities through two versions: v1 for pure vector search and v2 for multi-index hybrid keyword search with higher overhead but more features.

## Key Features

- **Quantized Vector Search**: Uses quantizers to reduce memory usage while maintaining search quality
- **Hybrid Search**: Combines vector and keyword search to find relevant documents
- **Filter Search**: Supports filtering based on queries or metadata
- **Simple REST API**: JSON or MessagePack based, no custom query language required
- **No Custom Clients**: Standard HTTP clients work out of the box

## Two Versions

### Version 1 (v1)
- Pure vector search implementation
- Lower overhead and simpler architecture
- Optimized for semantic similarity search

### Version 2 (v2)
- Multi-index implementation
- Hybrid keyword search support
- Higher overhead but more versatile
- Better for combining semantic and lexical matching

## API Design

SemaDB features a RESTful API that is:
- JSON or MessagePack based for efficient data transfer
- No need to learn a new query language
- Compatible with standard HTTP clients
- Easy integration with existing applications

## Use Cases

- Semantic search applications
- Hybrid retrieval combining keywords and vectors
- RAG implementations requiring metadata filtering
- Applications needing simple REST-based vector search
- Memory-constrained deployments with quantization

## Technical Features

- Vector quantization for reduced memory footprint
- Metadata filtering capabilities
- Support for multiple similarity metrics
- Efficient storage and retrieval

## Pricing

Open-source with self-hosting options.