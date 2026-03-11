## Overview

Apache Kvrocks is a distributed key-value NoSQL database that uses RocksDB as its storage engine and is compatible with the Redis protocol. Vector similarity search support is currently under active development.

## Vector Search Implementation (Experimental)

Kvrocks is integrating vector indexing capabilities to support vector similarity searches with real-time processing and efficient large-scale vector data management.

### Current Status

- **Experimental Feature**: Vector search via Kvrocks Search module (KQIR)
- **HNSW Algorithm**: Initial implementation focuses on on-disk HNSW index
- **Field Type**: VECTOR field type added to existing TAG and NUMERIC types
- **Production Status**: Under active development, not yet production-ready

## Vector Search Features

### Supported Query Types

- **Vector Range Queries**: `@vec_field:[VECTOR_RANGE range $vec]`
- **KNN Queries**: `* => [KNN n @vec_field $vec]` (without prefiltering)

### Vector Field Configuration

- **Data Type**: FLOAT64 vectors
- **Dimensionality**: Configurable vector dimensions
- **Distance Metrics**: L2 (Euclidean), IP (Inner Product), COSINE

### HNSW Parameters

- Initial capacity (default: 500,000)
- M parameter for maximum edges per node (default: 16)
- ef_construction (default: 200)
- ef_runtime (default: 10)
- Epsilon for approximate search (default: 0.01)
- Number of levels in the graph

## Core Kvrocks Features

- **Redis Compatibility**: Compatible with Redis protocol and commands
- **RocksDB Backend**: Persistent storage with RocksDB
- **Distributed Architecture**: Built for horizontal scaling
- **Disk-Based**: Lower memory requirements than in-memory databases
- **Kvrocks Search (KQIR)**: Query engine supporting SQL and RediSearch queries

## Use Cases

- **RAG Applications**: LangChain can utilize Kvrocks as a vector database
- **Large-Scale Vector Storage**: Cost-effective disk-based vector storage
- **Redis Migration**: Drop-in replacement for Redis with vector capabilities
- **Hybrid Workloads**: Combine key-value operations with vector search

## Architecture

Kvrocks Search encoding design efficiently maps HNSW index structures to RocksDB key-values, enabling persistent, scalable vector search on disk.

## Integration

- Redis client libraries (any language with Redis support)
- LangChain for RAG applications
- RediSearch-compatible tools
- SQL query interface via KQIR

## Roadmap

- Complete HNSW implementation
- Additional index types based on performance requirements
- Enhanced filtering capabilities
- Production-ready vector search module

## Pricing

Free and open-source under the Apache 2.0 license.