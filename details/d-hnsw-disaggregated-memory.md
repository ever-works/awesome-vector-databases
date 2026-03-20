## Overview

Published in May 2025 (arXiv:2505.11783), d-HNSW addresses efficient vector search in disaggregated memory architectures where compute nodes access memory over network.

## Disaggregated Memory Architecture

Modern cloud systems increasingly separate:
- **Compute**: CPU/GPU processing
- **Memory**: Remote memory accessed over network (RDMA)
- **Storage**: Persistent data

This enables flexible resource allocation but challenges traditional algorithms.

## Key Innovations

**Network-Aware Traversal**: Optimizes HNSW graph traversal for network latency

**Prefetching**: Anticipates needed nodes and fetches in batches

**Caching**: Intelligent caching of frequently accessed graph regions

**Batching**: Groups operations to amortize network overhead

## Benefits

- Efficient use of disaggregated resources
- Scalability beyond single-node memory
- Cost optimization in cloud environments
- Flexibility in resource allocation

## Use Cases

- Cloud-native vector databases
- Kubernetes-based deployments
- Serverless vector search
- Multi-tenant systems with resource sharing

## Availability

ArXiv preprint arXiv:2505.11783 (2025)