## Overview

As of version 25.6.2.5, ClickHouse supports vector similarity indexing using the HNSW algorithm, enabling high-performance approximate nearest-neighbor (ANN) searches within the analytical database.

## Supported ANN Index Types

### HNSW (Hierarchical Navigable Small World)
- Current state-of-the-art method for approximate vector search
- Based on hierarchical navigable small world graphs algorithm
- Implemented via the USearch library
- Standard for fast vector retrieval

### Annoy (Previously Supported)
- Based on the ANNOY library in C++ from Spotify
- Used in Spotify's music recommendations
- Currently experimental in ClickHouse

## Search Approaches

ClickHouse offers two main approaches for vector search:

1. **Brute-force search using distance functions**
   - Highly accurate but slower
   - No index required
   - Best for smaller datasets

2. **Indexing vector fields**
   - Faster but less precise
   - Uses ANN indexes (HNSW)
   - Suitable for large-scale deployments

## QBit Data Type

ClickHouse introduced a new data type QBit where no early decisions are needed and you can adjust precision and speed trade-off directly at query time. This allows for flexible optimization based on specific query requirements.

## Memory & Performance Considerations

- The vector similarity index must be fully loaded from disk into main memory to perform searches
- Vector index is constructed fully in memory and then saved to disk
- Provides fast retrieval for billion-scale vector datasets

## Use Cases

- Real-time analytics with vector search
- Recommendation systems
- Semantic search in data warehouses
- Combining analytical queries with similarity search
- Large-scale embedding storage and retrieval

## Architecture

ClickHouse's vector search is built into its MergeTree table engine family, allowing seamless integration with existing analytical workloads and SQL queries.

## Pricing

Free and open-source (Apache 2.0 license). Commercial cloud offerings available through ClickHouse Cloud.