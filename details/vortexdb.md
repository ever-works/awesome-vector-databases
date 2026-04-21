## Overview

VortexDB is organized as a Rust workspace with modular crates for indexers, storage, and clients.

## Indexers

- Flat: brute-force exact search for smaller datasets
- KD-Tree: space-partitioning for low-dimensional vectors
- HNSW: hierarchical navigable small world graphs for fast approximate nearest neighbor search on large datasets

Supported distance metrics: Euclidean, Manhattan, Hamming, Cosine.

## Storage Engine

Abstraction via StorageEngine trait. Supports RocksDB for persistent storage and in-memory option.

## Clients

### HTTP Server (Axum)
- GET / : Root endpoint
- GET /health : Health check
- POST /points : Insert point
- GET /points/:id : Get point by ID
- DELETE /points/:id : Delete point
- POST /points/search : Search similar vectors

### gRPC Server
High-performance with Protocol Buffers, full CRUD for vector points, configurable logging.

### TUI Client (Ratatui)
Interactive terminal UI with dashboard, database management, vector operations, modal dialogs.

## Deployment

Uses Dockerfile and docker-compose for unified gRPC/HTTP server startup. Key environment variables:

| Env Var | Function | Safe Default |
|---------|----------|--------------|
| HTTP_HOST | HTTP Server host | 0.0.0.0 |
| HTTP_PORT | HTTP Server port | 3000 |
| GRPC_HOST | gRPC Server host | 0.0.0.0 |
| GRPC_PORT | gRPC Server port | 50051 |
| STORAGE_TYPE | inmemory || rocksdb | inmemory |
| INDEX_TYPE | flat || kdtree || hnsw | flat |
| LOGGING | Enable logs | true |
| DISABLE_HTTP | Disable HTTP Server | false |

Required: GRPC_ROOT_PASSWORD, DIMENSION, DATA_PATH.

Commands: `docker compose up`, `docker compose up --build`.

## Roadmap

- In-memory StorageEngine implementation
- Snapshots for indexers
- Benchmarking suite
- Python SDK
- JavaScript/TypeScript SDK
- Modular vectorization service

## Pricing

Free and open-source under Apache License 2.0.