## Overview

pgvecto.rs delivers blazing-fast vector search in PostgreSQL via Rust, outperforming pgvector significantly.

## Features

- **Indexes**: Diskless HNSW (20x pgvector speed), DiskANN
- **Distances**: L2, cosine, inner product
- **Hybrid SQL**: Vectors + relational ops (filters, joins, aggs)
- **Quantization**: FP16/INT8/binary for efficiency
- **ACID/WAL**: Full Postgres guarantees

## Use Cases

- **RAG Pipelines**: Low-latency retrieval in app DB
- **Analytics**: Embeddings clustering, recommendations
- **Real-time**: High QPS semantic search

## Comparisons

**vs pgvector**: 20x faster HNSW, better concurrency.
**vs Weaviate**: No data sync, native SQL vs gRPC; Postgres scales via Citus.

## Pricing

Free open-source (PostgreSQL License).