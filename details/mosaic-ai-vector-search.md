# Mosaic AI Vector Search

**Website:** <https://docs.databricks.com/aws/en/vector-search/vector-search>

## Overview

Mosaic AI Vector Search is a managed vector search service built into the Databricks Data Intelligence Platform. It lets you create high‑capacity vector indices from Delta tables and query them via API for similarity search, supporting common AI workloads such as RAG, recommendation, and image/video search.

## Key Capabilities

- Create vector search indexes directly from Delta tables.
- Store embeddings together with associated metadata.
- Query indexes via REST API for approximate nearest neighbor (ANN) search.
- Configure automatic sync of indexes when the underlying Delta table changes.
- Support for hybrid keyword + similarity search.
- Support for filters and reranking on search results.
- Integration with Databricks governance, including ACLs on vector search endpoints.
- Option to sync only selected columns from source tables.
- Ability to save and reuse generated embeddings.

## Features

### Indexing & Data Model
- Build vector search indexes from Delta tables.
- Index contains:
  - Embedding vectors.
  - Associated source data/documents.
  - Arbitrary metadata columns.
- Configure automatic synchronization so changes in the Delta table are propagated to the index.
- Option to include only selected columns from the Delta table in the index.
- Support for storing and syncing previously generated embeddings.

### Similarity Search
- Uses Hierarchical Navigable Small World (HNSW) algorithm for approximate nearest neighbor search.
- Uses L2 (Euclidean) distance as the similarity metric.
- Cosine similarity achievable by normalizing embeddings before indexing/querying (L2 ranking matches cosine when vectors are normalized).
- Designed for high‑capacity, high‑performance similarity search across large collections of embeddings.

### Hybrid Keyword–Similarity Search
- Combines vector‑based similarity with traditional keyword search.
- Retrieves documents that:
  - Match query terms using keyword techniques.
  - Are semantically similar based on embeddings.
- Especially useful where data contains unique identifiers or tokens (for example, SKUs, IDs) that pure vector search may not handle well.

### Keyword Search Details
- Relevance scoring is based on Okapi BM25.
- All text/string columns are searchable, including:
  - The original source text used to generate embeddings.
  - Metadata columns stored as text or strings.
- Tokenization splits text into tokens (per the underlying implementation) for BM25 scoring.

### Querying & Result Control
- Query access via REST API.
- Supports:
  - Pure vector similarity search.
  - Pure keyword search (BM25).
  - Hybrid search combining both.
- Filtering on metadata fields when querying the vector index.
- Reranking of results to refine ordering after the initial similarity/keyword search.

### Security & Governance
- Integrated with Databricks access control.
- Access control lists (ACLs) can be applied to vector search endpoints.
- Leverages Databricks platform governance for managing who can query or modify vector search resources.

## Technology

- ANN algorithm: Hierarchical Navigable Small World (HNSW).
- Distance metric: L2 (Euclidean) distance for similarity ranking.
- Keyword ranking: Okapi BM25.

## Integrations & APIs

- Built into the Databricks Data Intelligence Platform.
- Works natively with Delta tables as the data source.
- API access via:
  - REST endpoints for querying vector search indexes.
  - Python SDK (`databricks.vector_search`), as documented in the Python SDK reference.

## Pricing

- No pricing information is provided in the referenced content.