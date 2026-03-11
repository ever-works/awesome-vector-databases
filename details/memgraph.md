## Overview

Memgraph is an in-memory graph database platform that features native vector search capabilities powered by USearch, a high-performance C++ library implementing the Hierarchical Navigable Small World (HNSW) index structure.

## Key Features

- **Native Vector Search**: Built-in vector search using HNSW algorithm (since version 3.2)
- **Single Platform**: Combines graph database and vector search in one system
- **Production Ready**: Fully supported with CREATE VECTOR INDEX, persists across restarts
- **High Performance**: In-memory architecture for fast graph traversal and vector queries
- **GraphRAG Support**: Seamless integration of vector embeddings with knowledge graphs

## Vector Search Implementation

### Index Types

Memgraph supports single-store vector index on nodes where:
- Vector values stored only in the vector index backend (USearch)
- Property store keeps references (vector index IDs)
- Efficient memory utilization

### Distance Metrics

Supports multiple similarity measures:
- Euclidean distance (L2)
- Cosine similarity
- Inner product

## GraphRAG Applications

Memgraph enables powerful GraphRAG patterns by combining:
- **Graph Database**: Stores entities and relationships for multi-hop reasoning
- **Vector Search**: Semantic similarity matching for natural language queries
- **Dynamic Updates**: Real-time knowledge graph updates

### Example Use Case: Biomedical Knowledge

- Store biomedical entities (genes, drugs, diseases) as graph nodes
- Vector embeddings for semantic search
- Relationship traversal for complex queries
- Multi-hop reasoning across connected entities

## Use Cases

- **RAG Systems**: Retrieval based on semantic similarity + graph context
- **Recommendation Engines**: User-item matching with relational context
- **Fraud Detection**: Pattern recognition with relationship analysis
- **Knowledge Discovery**: Uncover hidden insights through graph connections
- **Question Answering**: Combine semantic search with knowledge graphs
- **Research Tools**: Link semantically similar concepts across domains

## Integration

- Python client library
- Cypher query language (extended for vector operations)
- REST API
- Kafka, Pulsar streaming integrations
- LangChain compatibility for RAG workflows

## Technical Specifications

- **Storage**: In-memory with optional disk persistence
- **Query Language**: Cypher with vector extensions
- **Vector Index**: HNSW via USearch
- **Graph Processing**: Native property graph model
- **ACID Transactions**: Full transactional support

## Pricing

Memgraph offers:
- Open-source Community Edition (free)
- Enterprise Edition with advanced features
- Cloud-managed options

Contact sales for enterprise pricing details.