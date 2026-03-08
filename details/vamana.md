## Overview

Vamana is the algorithm behind the DiskANN solution, designed for disk-based vector indexing. It is a graph-based indexing structure that minimizes the number of sequential disk reads required for efficient approximate nearest neighbor search.

## Key Characteristics

### Graph Structure
- Vamana builds a flat graph, in contrast to HNSW which uses a hierarchical representation
- Creates a graph with smaller search "diameter" - the max distance between any two nodes
- Minimizes sequential disk reads through optimized graph topology

### Storage Approach
- Graph index along with full-precision vectors stored on disk
- Compressed vectors cached in memory
- Can be combined with vector compression schemes like product quantization

## Performance Advantages

### Recent Development (2025)
NVIDIA cuVS team provides DiskANN with Vamana algorithm built on GPU:
- 40x or greater speedup over CPU implementation
- Maintains search quality while dramatically improving build times

## Comparison with HNSW

While HNSW uses hierarchical layers for routing, Vamana uses a single-layer graph optimized for:
- Disk-based storage and access patterns
- Minimized I/O operations
- Efficient batch construction

## DiskANN Integration

Vamana is the core algorithm in Microsoft's DiskANN, which:
- Handles billion-scale datasets
- Provides real-time search with simple filters
- Used extensively at Microsoft in Bing and Microsoft 365
- Available on Azure Database for PostgreSQL

## Applications

- Large-scale vector search requiring disk storage
- Cost-effective billion-scale deployments
- Production systems needing high accuracy with limited memory