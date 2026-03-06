## Overview

pgvecto.rs is a Postgres extension written in Rust that provides scalable, low-latency, hybrid-enabled vector search. Built on the pgrx framework, it offers significant performance improvements over pgvector while maintaining PostgreSQL compatibility.

## Key Features

- **High Performance**: HNSW algorithm 20x faster than pgvector at 90% recall
- **Multiple Data Types**: FP16 (16-bit float), INT8 (8-bit integer), binary vectors
- **WAL Support**: Write-Ahead Logging for index and data durability
- **Filtering Support**: Advanced filtering during search and retrieval
- **Memory Safety**: Rust's compile-time checks guarantee memory safety
- **Hybrid Search**: Combines vector and traditional search capabilities

## Why Rust?

Rust provides:
- Memory safety without garbage collection
- Prevention of entire classes of bugs and security issues
- Better performance than C extensions
- Modern development experience with cargo ecosystem

## Performance Comparison

At 90% recall:
- **20x faster** than pgvector HNSW
- Lower latency for production workloads
- Better resource utilization

## Data Type Support

- **FP32**: Standard 32-bit floating point
- **FP16**: 16-bit floating point for reduced memory
- **INT8**: 8-bit integers for compact storage
- **Binary**: Binary vectors for maximum compression

## Technical Architecture

- Built on pgrx framework for Postgres extensions
- Native Rust implementation for performance
- Integrates with PostgreSQL query planner
- WAL support for durability and replication

## Getting Started

### Docker (Recommended)
```bash
docker run \
  --name pgvecto-rs-demo \
  -e POSTGRES_PASSWORD=mysecretpassword \
  -p 5432:5432 \
  -d ghcr.io/tensorchord/pgvecto-rs:pg17-v0.4.0
```

### Installation
- Pre-built binaries available
- Source compilation with cargo
- Docker images for all major PostgreSQL versions

## Use Cases

- Large-scale vector search (millions to billions of vectors)
- Low-latency production applications
- Applications requiring multiple vector data types
- Hybrid search combining vectors with metadata
- PostgreSQL-native AI applications

## Documentation

Comprehensive documentation at: https://docs.vectorchord.ai/

## Repository

GitHub: tensorchord/pgvecto.rs
Docker Hub: tensorchord/pgvecto-rs

## Pricing

Free and open-source. No licensing costs for self-hosted deployments.