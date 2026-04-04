## Overview

Memgraph is an in-memory graph database platform that features native vector search capabilities powered by USearch, a high-performance C++ library implementing the Hierarchical Navigable Small World (HNSW) index structure.

## Key Features

- **Native Vector Search**: Built-in vector search using HNSW algorithm (since version 3.2)
- **Single Platform**: Combines graph database and vector search in one system
- **Production Ready**: Fully supported with CREATE VECTOR INDEX, persists across restarts
- **High Performance**: In-memory architecture for fast graph traversal and vector queries
- **GraphRAG Support**: Seamless integration of vector embeddings with knowledge graphs

## GraphRAG Applications

Memgraph enables powerful GraphRAG patterns by combining:
- **Graph Database**: Stores entities and relationships for multi-hop reasoning
- **Vector Search**: Semantic similarity matching for natural language queries
- **Dynamic Updates**: Real-time knowledge graph updates

## Integration

- Python client library
- Cypher query language (extended for vector operations)
- REST API
- Kafka, Pulsar streaming integrations
- LangChain compatibility for RAG workflows

## Pricing

Memgraph offers:
- Open-source Community Edition (free)
- Enterprise Edition with advanced features
- Cloud-managed options

Contact sales for enterprise pricing details.