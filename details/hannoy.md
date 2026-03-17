## Overview

Hannoy is a graph-based successor to Arroy (Meilisearch's tree-based ANN library), designed to combine the best aspects of graph-based approximate nearest neighbor search with KV-backed storage via LMDB. It represents the next evolution in Meilisearch's vector search technology.

## Design Goals

Hannoy aims to combine:
- **Graph-based ANN**: Superior search performance of graph algorithms
- **LMDB Storage**: Production-ready persistent key-value storage
- **Production Features**: The reliability and update capabilities of Arroy

## Evolution from Arroy

### Arroy (Previous Generation)
- Tree-based LSH (Locality Sensitive Hashing) approach
- Built on LMDB for persistent storage
- Incremental updates without full rebuilds
- Memory-mapped for multi-process sharing

### Hannoy (Current Generation)
- Graph-based algorithms (similar to HNSW)
- Maintains LMDB backend
- Enhanced search performance (approximately 10x faster)
- Retains production-ready features from Arroy

## Key Features

- **Graph-Based Search**: Uses graph algorithms for more efficient nearest neighbor search
- **LMDB Backend**: Persistent, memory-mapped storage for reliability and multi-process access
- **Incremental Updates**: Support for updating indexes without expensive rebuilds
- **Production-Ready**: Designed for use in production environments like Meilisearch
- **Memory Efficiency**: Optimized for applications with millions of high-dimensional vectors

## Performance Improvements

Blog posts suggest that moving from tree-based (Arroy) to graph-based (Hannoy) algorithms can provide up to 10x speedup in vector search performance while maintaining the same storage and update characteristics.

## Use in Meilisearch

Hannoy is being developed as part of Meilisearch's vector search capabilities to:
- Handle millions of documents with high-dimensional embeddings (768-1536 dimensions)
- Provide fast incremental updates as content changes
- Maintain low memory footprint
- Support multi-modal search (text and images)

## Technical Architecture

- **Storage**: LMDB (Lightning Memory-Mapped Database)
- **Algorithm**: Graph-based ANN (similar to HNSW)
- **Language**: Rust
- **Integration**: Built into Meilisearch's vector search stack

## Distance Metrics

Likely supports similar metrics to Arroy:
- Euclidean distance
- Manhattan distance
- Cosine distance
- Dot (Inner) Product distance

## Resources

- **Blog**: https://blog.kerollmops.com/from-trees-to-graphs-speeding-up-vector-search-10x-with-hannoy
- **Related**: Arroy at https://github.com/meilisearch/arroy
- **Developer**: Developed by the Meilisearch team

## Significance

Hannoy represents the evolution of LMDB-backed vector search from tree-based to graph-based algorithms, maintaining production features while achieving significant performance improvements. It demonstrates how modern vector databases can combine cutting-edge algorithms with robust, persistent storage systems.