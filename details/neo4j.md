## Overview

Neo4j is a native graph database platform that combines powerful graph data management with vector search capabilities, enabling hybrid graph+vector queries for knowledge-intensive AI applications.

## Features

- **Native Graph Storage**: Purpose-built graph data storage with connected data structures
- **Cypher Query Language**: Declarative query language optimized for graph patterns
- **Vector Search Index**: Native vector index support (available since v5.13) for embedding-based similarity search
- **GraphRAG**: Hybrid graph + vector retrieval augmented generation for improved context retrieval
- **Embedding Storage**: Embeddings stored as properties on graph nodes with native indexing
- **Similarity Metrics**: Supports Euclidean distance and cosine similarity
- **Top-K Search**: Retrieve top-N similar nodes ranked by similarity score
- **Hybrid Queries**: Combine graph traversals with vector similarity in a single Cypher query

## Vector Search Capabilities

- **Vector Index Creation**: `CALL db.index.vector.createNodeIndex(...)`
- **Vector Property Storage**: `CALL db.create.setNodeVectorProperty(...)`
- **Similarity Queries**: `CALL db.index.vector.queryNodes(...)` for nearest-neighbor lookups
- **Index Parameters**: Configurable dimensions, similarity functions, and index size
- **Integration with Graph Context**: Vectors linked to graph topology enables context-aware retrieval

## Knowledge Graph Applications

- Semantic search with graph structure context
- Entity resolution and disambiguation
- Recommendation engines with rich relationship data
- Fraud detection with pattern matching over connected data
- Question answering over structured knowledge bases

## Ecosystem

- **Aura**: Fully managed cloud database service
- **Neo4j Desktop**: Local development environment
- **Drivers**: Official drivers for Python, Java, JavaScript, Go, .NET, and more
- **GraphQL**: Neo4j GraphQL Library for schema-first development
- **MCP Server**: Available for AI agent integrations

## Pricing

- **Community Edition**: Free, self-hosted with core features
- **AuraDB Free**: Free managed tier for development
- **AuraDB Standard/Professional**: Cloud-managed with production SLAs
- **Neo4j Enterprise**: Self-hosted enterprise with full feature set
- Detailed pricing at: neo4j.com/pricing