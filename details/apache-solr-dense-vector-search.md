## Overview

Apache Solr's Dense Vector Search adds support for indexing and searching dense numerical vectors, enabling k-nearest neighbor (kNN) searches with various similarity functions and advanced filtering capabilities.

## Recent Enhancements (2025-2026)

### Early Termination Strategy

Apache Solr 10.0.0 introduces PatienceKnnVectorQuery that allows searches to exit early when the HNSW queue remains saturated over a saturation threshold, reducing query latency and resource usage with minimal impact on recall.

### Text-to-Vector Module

Solr 9.8 introduced a module enabling transparent end-to-end semantic search by integrating with LLM providers (OpenAI, Cohere, HuggingFace, Mistral AI) via LangChain4j library.

### ACORN Algorithm

ACORN is an algorithm designed to make hybrid searches consisting of a filter and a vector search more efficient, based on research from 2024.

## Core Functionality

- **HNSW Indexing**: Hierarchical Navigable Small World graphs for efficient ANN search
- **Multiple Similarity Functions**: Support for cosine, dot product, and euclidean distance
- **Filtered Search**: Combine vector search with traditional Solr queries
- **Seeded Queries**: Start vector search from specific points
- **Hybrid Search**: Semantic fusion combining keyword and vector search

## Performance Optimizations

- Early termination for faster queries
- Configurable HNSW parameters (M, efConstruction)
- Batch indexing support
- Query-time optimization strategies

## Integration Capabilities

- LangChain4j for LLM provider integration
- Support for OpenAI, Cohere, HuggingFace, Mistral AI embeddings
- REST API for all operations
- Compatible with existing Solr ecosystem

## Use Cases

- Hybrid search combining keywords and semantics
- E-commerce product search with image similarity
- Document retrieval with semantic understanding
- Recommendation systems
- Question-answering applications

## Pricing

Free and open-source under Apache 2.0 license. No licensing costs for any use case.