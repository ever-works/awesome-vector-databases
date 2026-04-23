## Overview

PostgreSQL-compatible distributed SQL database with built-in vector search capabilities using HNSW indexing. Supports ACID transactions, horizontal sharding, and auto-rebalancing to scale vector workloads from millions to billions of embeddings for AI and GenAI applications.

## Hybrid Capabilities

- Vector similarity + SQL keyword/full-text + joins/aggs.
- Post-query reranking via SQL windows.

## Key Features

Combines vector similarity search with relational queries including joins and aggregations.

## Use Cases

- Multimodal RAG blending embeddings with relational data.

## Comparisons vs Pure Vector DBs (e.g., Qdrant)

| Feature | YugabyteDB | Pure Vector DB |
|---------|------------|----------------|
| SQL Hybrid | Full Postgres+vector | Vector only |
| ACID Scale | Distributed | Often single-node |

## Pricing

Open source core; enterprise features available.