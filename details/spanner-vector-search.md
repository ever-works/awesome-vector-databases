## Overview

Vector search in Spanner is a high-performance, built-in capability that enables semantic search and similarity matching on high-dimensional vector data. By storing and indexing vector embeddings directly within your transactional database, Spanner eliminates the need for separate vector databases and complex ETL pipelines.

## Recent Developments (2025-2026)

In 2025, Spanner made significant advancements with new functionality across graph, vector, and text search, as well as Vertex AI integrations, including using graphs with vector search for GraphRAG use-cases. Google has "a lot more exciting capabilities lined up for 2026."

## Key Features

### Availability
Vector search is available with the Spanner Enterprise edition and Enterprise Plus edition.

### Search Methods
- K-nearest neighbors (KNN) for exact search by calculating the distance between the query and every vector in the dataset
- Approximate nearest neighbors (ANN) for use cases like similarity search or retrieval-augmented generation for generative AI applications

### Distance Functions
Spanner Graph supports:
- COSINE_DISTANCE()
- EUCLIDEAN_DISTANCE()
- DOT_PRODUCT()

## Hybrid Search Capabilities

Hybrid search combines the precision of keyword matching (full-text search, FTS) with the recall of semantic matching (vector search) to produce highly relevant search results.

## AI Integration

Spanner now includes built-in AI integrations:
- ML.PREDICT for natural language queries
- Vertex RAG Engine lets you use Spanner as a RAG-managed database for data indexing and retrieval operations
- Direct integration with Vertex AI Vector Search for export workflows

## Use Cases

- Retrieval-Augmented Generation (RAG) applications
- Semantic search combining transactional and vector data
- GraphRAG implementations using graphs with vector search
- Enterprise applications requiring ACID guarantees with vector search

## Performance & Scale

As a globally distributed database, Spanner provides:
- High-performance vector search at scale
- Strong consistency guarantees
- Integration with existing transactional workloads
- Built-in replication and disaster recovery

## Pricing

Pricing based on Spanner Enterprise or Enterprise Plus edition. Consult Google Cloud pricing documentation for details.