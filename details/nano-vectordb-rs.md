## Overview

nano-vectordb-rs is a Rust port of the popular nano-vectordb, designed as a lightweight vector database.

## Features

- Fast cosine similarity searches using Rayon parallelism
- Simple API surface
- Embedded persistence with compact serialization
- No abstractions, easy to hack

## Use Cases

- Rust ML pipelines needing lightweight vector storage
- Prototyping semantic search systems
- Educational use

## Benchmarks

On MacBook M4 with 1024-dim embeddings:
- Inserting 100,000 vectors: ~175 ms
- Querying from 100,000 vectors: ~13 ms

## Installation

```
cargo install nano-vectordb-rs
```

## Examples

Basic usage example available via `cargo run --example basic_usage`.
Advanced example with Hugging Face embeddings: `cargo run --example advanced_usage`.