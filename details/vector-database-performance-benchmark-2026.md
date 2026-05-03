## Overview

Q1 2026 benchmark of 10 vector databases: ChromaDB, Elasticsearch, Milvus, MongoDB Atlas, Pinecone, pgvector, Qdrant, Redis, Supabase, Weaviate. Evaluates latency, throughput, scaling, deployment options, features, and pricing under standardized conditions (1M vectors, 1536 dims).

## Performance Metrics

| Database | p50 (ms) | p99 (ms) | Throughput (vectors/sec) | Max Vectors | Max Dims |
|----------|----------|----------|---------------------------|-------------|----------|
| Qdrant | 4 | 25 | 8,000-20,000 | Billions (distributed) | 65,536 |
| Redis | 5 | 20 | 15,000-40,000 | 10-100M (RAM-bound) | 32,768 |
| Milvus | 6 | 35 | 10,000-30,000 | Billions+ (distributed) | 32,768 |
| Pinecone | 8 | 45 | 5,000-15,000 | Billions | 20,000 |
| ChromaDB | 12 | 70 | 2,000-8,000 | <1M (single node) | 65,536 |
| Weaviate | 12 | 65 | 3,000-10,000 | Billions (managed) | 65,535 |
| Elasticsearch | 15 | 75 | 5,000-15,000 | Billions (distributed) | 4,096 |
| pgvector | 18 | 90 | 1,000-5,000 | 10-50M (single node) | 16,000 |
| Supabase | 20 | 95 | 1,000-5,000 | 10-50M (plan-dependent) | 16,000 |
| MongoDB Atlas | 22 | 110 | 3,000-10,000 | Billions (Atlas) | 4,096 |

## Features

| Database | Hybrid Search | Multi-Tenancy | ACID | Index Types | Distance Metrics | SDK Languages |
|----------|---------------|---------------|------|-------------|------------------|---------------|
| ChromaDB | No | No | No | HNSW | cosine, L2, inner product | Python, TypeScript, REST |
| Elasticsearch | Yes | Yes | No | HNSW | cosine, dotProduct, L2 | Python, Node.js, Java, Go, Ruby, PHP, Rust, .NET, REST |
| Milvus | Yes | Yes | No | HNSW, IVF_FLAT, IVF_SQ8, IVF_PQ, SCANN, DiskANN, GPU_IVF_FLAT, GPU_IVF_PQ | cosine, L2, inner product | Python, Node.js, Go, Java, C#, REST, gRPC |
| MongoDB Atlas | Yes | Yes | No | HNSW | cosine, euclidean, dotProduct | Python, Node.js, Java, Go, C#, Ruby, PHP, Rust, Swift, Kotlin, REST |
| Pinecone | Yes | Yes | No | Proprietary | cosine, dotProduct, euclidean | Python, Node.js, Java, Go, REST |
| pgvector | Yes | Yes | Yes | HNSW, IVFFlat | cosine, L2, inner product | Python, Node.js, Ruby, Go, Java, C#, PHP, Any SQL client |
| Qdrant | Yes | Yes | No | HNSW | cosine, dot, euclidean, manhattan | Python, TypeScript, Rust, Go, Java, .NET, REST, gRPC |
| Redis | Yes | No | No | HNSW, FLAT | cosine, L2, inner product | Python, Node.js, Java, Go, C#, Ruby, REST |
| Supabase | Yes | Yes | Yes | HNSW, IVFFlat | cosine, L2, inner product | TypeScript, Python, Dart, Swift, Kotlin, C#, REST |
| Weaviate | Yes | Yes | No | HNSW, flat, dynamic | cosine, dot, L2-squared, hamming, manhattan | Python, TypeScript, Go, Java, REST, GraphQL |

## Pricing (Managed Starting Prices)

- Redis Cloud: $7/mo (free tier 30MB)
- Qdrant Cloud: $9/mo (free tier 1GB)
- Supabase Pro: $25/mo (free tier 500MB)
- Weaviate Cloud: $25/mo (free tier)
- MongoDB Atlas: $57/mo (free tier 512MB)
- Zilliz Cloud (Milvus): $65/mo (free tier)
- Pinecone: $70/mo (free tier 2GB)
- Elastic Cloud: $95/mo (free trial)

Self-hosted open-source options (ChromaDB, Elasticsearch, Milvus, pgvector, Qdrant, Redis, Supabase, Weaviate) are free.

## Methodology

Tested on 1M vectors (1536 dims, OpenAI ada-002), AWS r6g.xlarge for self-hosted, standard tiers for managed (US-East). Median of 3 runs. License: CC BY 4.0.