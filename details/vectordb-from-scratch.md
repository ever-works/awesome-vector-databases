## Overview

vectordb-from-scratch is a from-scratch vector database in Rust featuring vector storage, indexing, search, persistence, HTTP API, and CLI.

## Features

- Vector storage with CRUD operations and string-based IDs
- Distance metrics: Euclidean, Cosine, Dot Product
- Brute-force search (FlatIndex) and approximate nearest neighbor search (HNSW)
- Metadata filtering with composable filter expressions (eq, ne, exists, and, or)
- Batch operations for bulk inserts and parallel searches
- Persistence with write-ahead log (WAL), snapshots, and crash recovery
- HTTP API (9 endpoints) powered by Axum
- Metrics collection with latency percentiles and operation counters
- CLI for direct interaction and running the HTTP server
- 89 tests including unit, integration, recall, and doc tests

## Index Types

- **FlatIndex**: Brute-force O(n) search. Exact results.
- **HnswIndex**: Hierarchical Navigable Small World graphs. >95% recall, faster on large datasets. Defaults: m=16, ef_construction=200, ef_search=50, max_layers=16.

## Persistence

- Write-Ahead Log (WAL): Durable logging with bincode and CRC32 checksums.
- Snapshots: Periodic checkpoints (default every 1,000 WAL entries).
- Crash Recovery: Loads latest snapshot and replays WAL.
- Optional memory-mapped I/O for snapshots.

## HTTP API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | /vectors | Insert a vector (with optional metadata) |
| GET | /vectors | List all vector IDs |
| GET | /vectors/:id | Get a vector by ID |
| DELETE | /vectors/:id | Delete a vector |
| POST | /vectors/batch | Batch insert vectors |
| POST | /search | Search for similar vectors (with optional filter) |
| POST | /search/batch | Batch search queries |
| GET | /health | Health check with vector count |
| GET | /metrics | Query latency percentiles and operation counters |

## Metadata Filters

Composable JSON expressions:
- `{"op": "eq", "field": "color", "value": "red"}`
- `{"op": "ne", "field": "color", "value": "blue"}`
- `{"op": "exists", "field": "category"}`
- `{"op": "and", "filters": [...]}`
- `{"op": "or", "filters": [...]}`

## Installation and Usage

Uses Nix with flakes. Enter dev shell with `nix develop`. Build with `cargo build --release`. Run CLI commands like `cargo run -- insert v1 --vector "1.0,2.0,3.0"`. Start server with `cargo run -- serve`.

## Benchmarks

Run with `cargo bench` to compare FlatIndex and HNSW.

## License

MIT License.