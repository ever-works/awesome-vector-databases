## Overview

hnswlib-rs is a pure-Rust implementation of the HNSW (Hierarchical Navigable Small World) algorithm inspired by the original C++ hnswlib. Designed with a decoupled architecture separating graph structure from vector storage.

## Key Features

- **Decoupled Architecture**: Graph separated from vector storage for flexibility
- **External Key Support**: Map your external keys to internal NodeId
- **Multiple Precision**: f32, f16, bf16, and per-vector quantized int8
- **Pure Rust**: Memory-safe implementation without C dependencies
- **Flexible Storage**: Provide vectors on demand via VectorStore interface

## Architecture

The library intentionally decouples components:
- `Hnsw<K, M>`: Owns the graph + mapping from external key K to internal NodeId
- `VectorStore`: Keyed by NodeId, supplies vectors on demand
- This design allows flexible storage backends and memory management

## Supported Data Types

- **f32**: Standard 32-bit floating point
- **f16**: 16-bit floating point for memory efficiency
- **bf16**: Brain floating point for ML applications
- **int8**: Quantized 8-bit integers for maximum compression

## Use Cases

- Approximate nearest neighbor search
- Embedding similarity search
- Large-scale vector retrieval
- Custom storage backend integration
- Applications requiring memory-efficient vector search

## Installation

Available on crates.io:
```toml
[dependencies]
hnswlib-rs = "*"
```

## Comparison to Other Implementations

### vs. C++ hnswlib
- Memory safety guarantees from Rust
- No C dependencies or FFI overhead
- Modern Rust ecosystem integration

### vs. Other Rust HNSW
- Unique decoupled architecture
- Flexible vector storage
- Support for multiple precision formats

## Repository

GitHub: jean-pierreBoth/hnswlib-rs
Crates.io: https://crates.io/crates/hnswlib-rs

## Technical Details

Implements the algorithm from:
"Efficient and robust approximate nearest neighbor search using Hierarchical Navigable Small World graphs" by Yu. A. Malkov and D. A. Yashunin

## Pricing

Free and open-source under MIT or Apache 2.0 license. No licensing costs.