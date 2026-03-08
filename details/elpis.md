## Overview

ELPIS is a graph-based similarity search algorithm for scalable data science, published in Proceedings of the VLDB Endowment 16.6 (2023): 1548-1559.

## Key Performance Metrics

### Index Building
- Builds index 3x-8x faster than competitors
- Uses 40% less memory than competing methods

### Query Performance
- Achieves high recall of 0.99
- Up to 2x faster than state-of-the-art methods
- Answers 1-NN queries up to one order of magnitude faster
- 3x faster than graph-based method EFANNA
- Returns same answer as serial scan and QALSH but over three orders of magnitude faster

## Technical Approach

### DC Strategy with II and ND
- Adopted Divide-and-Conquer (DC) strategy
- Leverages both Iterative Improvement (II) and Neighbor Diversification (ND)
- Maintains graphs separately and searches them in parallel

### Graph Construction
ELPIS uses the same search algorithm as other state-of-the-art graph-based methods (HNSW, NSG, etc.) but differs in:
- How it constructs the graph
- How it selects seed points
- Parallel graph maintenance and search

## Research Impact (2025-2026)

ELPIS is cited among state-of-the-art graph-based vector search methods in recent comprehensive evaluations:
- "Graph-Based Vector Search: An Experimental Evaluation of the State-of-the-Art" (February 2025)
- Included in comparisons with HNSW, NSG, HCNNG, and other leading algorithms

## Authors

Azizi, Ilias, Karima Echihabi, and Themis Palpanas (2023)

## Use Cases

- Scalable data science applications
- Large-scale similarity search
- High-dimensional nearest neighbor search
- Applications requiring fast index building
- Memory-constrained environments

## Comparison with Competitors

ELPIS offers an excellent balance:
- Faster index building than most competitors
- Lower memory usage
- Competitive or superior query performance
- High recall guarantees