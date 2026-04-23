## Overview

Milvus Distributed is the production-ready cluster mode of the open-source Milvus vector database, built for massive scale GenAI and similarity search workloads.

## Scalability

- Sharding across query, data, and index nodes for horizontal scaling
- High QPS handling (thousands to tens of thousands queries/sec)
- Kubernetes Helm deployment with auto-scaling

## Key Features

- High Availability (HA) with leaderless replication and automatic failover
- Real-time data ingestion and dynamic updates
- Hybrid search combining vector similarity with scalar filtering
- Support for HNSW, IVF, PQ, SCANN indexes
- Comprehensive ops tools: CLI, Attu UI, backup/restore, sizing calculator

## Use Cases

- Enterprise RAG pipelines at scale
- Multimodal search (text, image, audio)
- Drug discovery and genomics similarity
- Real-time recommendation systems

## Comparisons

Vs Qdrant distributed: Milvus provides broader index algorithms, mature Kubernetes tooling, and larger ecosystem; Qdrant emphasizes Rust performance and simpler single-binary clustering for high-throughput distrib setups.

## Pricing

Free open-source (Apache 2.0). Managed via Zilliz Cloud with pay-as-you-go pricing.