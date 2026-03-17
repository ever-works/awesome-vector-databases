## Overview

PUFFINN (Parameterless and Universal Fast FInding of Nearest Neighbors) is a parameterless LSH-based index for solving the k-nearest neighbor problem with probabilistic guarantees. It provides an easily configurable library for finding approximate nearest neighbors of arbitrary points.

## Key Features

- **Parameterless Design**: Users only need to specify memory usage and desired result quality (recall), not complex algorithm parameters
- **Probabilistic Guarantees**: Each near neighbor is guaranteed to be found with the specified recall probability, regardless of query difficulty
- **LSH-Based**: Uses Locality Sensitive Hashing with an adaptive query mechanism
- **Multiple Similarity Measures**: Supports Cosine similarity (SimHash/cross-polytope LSH) and Jaccard similarity (MinHash)
- **Multi-Language Support**: Available in both C++ and Python with feature parity

## Technical Approach

Under the hood, PUFFINN uses Locality Sensitive Hashing (LSH) with an adaptive query mechanism. This approach provides:
- Configurable memory budgets
- Adjustable recall levels
- Consistent performance across different query types

## Distance Functions

### Currently Supported:
- **Cosine Similarity**: Using SimHash or cross-polytope LSH
- **Jaccard Similarity**: Using MinHash

## Implementation

- **Languages**: C++ (primary implementation) with Python bindings
- **License**: Open source
- **Platform**: Cross-platform support

## Use Cases

- Applications requiring guaranteed recall rates
- Similarity search with predictable performance
- Systems where parameter tuning overhead should be minimized
- Cosine similarity search (text embeddings, document similarity)
- Jaccard similarity search (set similarity, recommendation systems)

## Academic Background

Published at the 27th Annual European Symposium on Algorithms (ESA 2019)

**Authors**: Martin Aumüller, Tobias Christiani, Rasmus Pagh, and Michael Vesterli

**Paper**: Available on arXiv (arXiv:1906.12211)

## Benchmarks

PUFFINN has been included in various ANN benchmarking efforts and demonstrates competitive performance with probabilistic quality guarantees.

## Resources

- **GitHub**: https://github.com/puffinn/puffinn
- **Publication**: ESA 2019 (27th Annual European Symposium on Algorithms)
- **arXiv**: 1906.12211

## Advantages

The parameterless design makes PUFFINN particularly attractive for developers who want:
- Simple configuration (just memory and recall)
- Guaranteed search quality
- No need for extensive parameter tuning
- Predictable behavior across different datasets