## Overview

Vector indexes accelerate similarity search by organizing vectors for efficient retrieval, trading perfect accuracy for speed.

## Index Categories

### Graph-Based

- **HNSW**: Hierarchical navigable small world
- **NSG**: Navigable Small World Graph
- **Vamana**: DiskANN algorithm

Best for: High recall, fast queries

### Clustering-Based

- **IVF**: Inverted File Index
- **IVF-PQ**: With product quantization
- **IVF-FLAT**: No compression

Best for: Large scale, memory efficiency

### Hash-Based

- **LSH**: Locality-Sensitive Hashing
- **Random Projection**: Dimensionality reduction

Best for: Very high dimensions, streaming data

### Tree-Based

- **Annoy**: Approximate Nearest Neighbors Oh Yeah
- **KD-Tree**: K-dimensional trees
- **Ball-Tree**: Metric trees

Best for: Low-medium dimensions

## Selection Criteria

- **Dataset size**: Billions vs millions
- **Dimensionality**: Low vs high
- **Query latency**: Real-time vs batch
- **Memory constraints**: RAM availability
- **Update frequency**: Static vs dynamic

## Pricing

Algorithms, no licensing.