## Overview

Turso brings native vector search to SQLite through its libSQL fork, eliminating the need for separate vector databases. Vector Similarity Search is built in as a native feature with no extension required.

## Key Features

- **Native Integration**: Vector datatype built directly into libSQL, skipping extension hooks
- **Vector Types**: Supports six vector types including FLOAT32, FLOAT16, FLOATB16, and 1-bit quantization
- **Distance Functions**: Dedicated vector functions like `vector_distance_cos` for similarity calculations
- **Vector Indexing**: Special vector index using DiskANN algorithm for approximate nearest neighbors
- **Hybrid Queries**: Combine relational and vector data in complex queries
- **Edge-Ready**: Scale to millions of agents with unlimited databases

## Use Cases

- RAG (Retrieval Augmented Generation) workflows
- AI apps requiring local-first architecture
- Recommendation engines
- Mobile applications with on-device inference
- Semantic search applications

## Architecture

Built on libSQL, a SQLite fork that enables adding native datatypes and operations for vectors, providing better performance than extension-based approaches.

## Pricing

Commercial solution with free tier:
- **Free Tier**: Available for development and small projects
- **Paid Tiers**: Based on usage and scale, contact sales for enterprise pricing