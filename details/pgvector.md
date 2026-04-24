## Overview

pgvector brings efficient vector search to PostgreSQL using standard SQL, eliminating the need for separate vector databases.

## Features

- **Indexes**: HNSW (high recall, dynamic), IVFFlat (scalable IVF)
- **Operators**: <-> (L2), <#> (negative inner product), <=> (cosine)
- **Hybrid SQL**: Full PostgreSQL expressivity - WHERE, JOIN, GROUP BY with vectors
- **Optimizations**: Binary quantization (pgv_512), GPU accel (experimental)

## Use Cases

- **RAG in DB**: Embed/retrieve context alongside app data
- **Analytics**: Clustering, anomaly detection on embeddings
- **Search**: Semantic/hybrid in CRM, ecomm

## Comparisons

**vs Weaviate**: Native Postgres ACID/SQL vs GraphQL/REST; no sync latency, lower ops cost. Scales via pg_shard or Citus; dedicated DBs better for pure vector QPS extremes.

## Pricing

Free open-source (PostgreSQL License).