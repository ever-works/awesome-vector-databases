## Overview

Vald is an open-source distributed fast ANN search engine for large-scale vector data, leveraging NGT indexing in a cloud-native microservices architecture.

## Scalability

- Distributed sharding across ngt agents for billions of vectors
- High QPS with low-latency ANN search
- Horizontal scaling on Kubernetes with auto-rebalancing

## Key Features

- High Availability via multi-replica indexes and failover rebalancing
- Asynchronous auto-indexing without downtime
- Automatic backups to object storage/PVs
- Customizable ingress/egress filtering
- gRPC-based with multi-lang SDKs (Go, Java, Python, Node)

## Use Cases

- Enterprise RAG and semantic search at scale
- Real-time image/video retrieval
- Recommendation engines
- Dynamic data updates in production

## Comparisons

Vs Milvus/Qdrant for distributed: Vald is lightweight Go-based with NGT specialization and simple k8s ops; Milvus has richer indexes/ecosystem, Qdrant Rust speed for filtering-heavy workloads.

## Pricing

Free open-source.