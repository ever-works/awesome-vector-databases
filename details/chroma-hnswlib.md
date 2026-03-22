## Overview

Chroma-hnswlib is Chroma's fork of the hnswlib library, optimized specifically for ChromaDB's vector indexing requirements. It serves as the core HNSW indexing engine powering Chroma's vector similarity search.

## Adoption

- **Weekly Downloads**: 408,522 (as of 2024)
- **Latest Version**: 0.7.6 (July 2024)
- **Platform Support**: Windows, macOS, and Linux with multiple Python versions

## Key Features

- **HNSW Algorithm**: Hierarchical Navigable Small World graph-based indexing
- **Performance Optimized**: Tailored for Chroma's specific use cases
- **Multi-Platform**: Prebuilt wheels for major operating systems
- **Python Integration**: Native Python bindings for ease of use

## Platform Availability

- Linux (multiple distributions)
- macOS (Intel and Apple Silicon)
- Windows
- Python 3.8 through 3.11+

## Integration

Automat ically installed as a dependency when using ChromaDB. Can also be used standalone for custom vector indexing implementations.

## Use Cases

- Core indexing for ChromaDB deployments
- Custom HNSW implementations in Python
- High-performance ANN search in Python applications
- Research and experimentation with HNSW parameters