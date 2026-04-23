# Lantern

Lantern is a PostgreSQL extension and toolkit for efficient vector search with disk persistence, scaling to billions of vectors.

## Disk Persistence vs In-Memory

Leverages PostgreSQL's disk storage for indexes, supporting out-of-core operations on large datasets exceeding RAM. Unlike standalone in-memory vector DBs, integrates with existing relational storage for persistent vectors.

## Key Features

- Tiered HNSW indexing
- SIMD-optimized queries for sub-ms latency
- Hybrid vector + BM25 text search
- Serverless offloaded indexing
- Embedding/LLM integration via SQL

## Use Cases

- Large-scale embeddings in databases
- Real-time AI applications
- Hybrid search on persistent data

## Comparisons

**DiskANN vs HNSW integration**: Builds on HNSW but adds disk persistence and tiering for larger scales; DiskANN more focused on pure graph out-of-core, Lantern on DB integration.

## Pricing

- Free tier: $0/month (multi-tenant)
- Self-hosted open-source
- Managed service available.