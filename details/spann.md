## Overview

SPANN (Highly-efficient Billion-scale Approximate Nearest Neighbor Search) is a memory-disk hybrid vector indexing and search system developed by Microsoft Research that follows the inverted index methodology.

## Architecture

SPANN stores only the centroid points of posting lists in memory while putting the large posting lists on disk. This hybrid approach enables efficient billion-scale vector search with reduced memory requirements.

## Performance

- Significantly outperforms DiskANN in both recall@1 and recall@10
- More than 2x faster than DiskANN, especially in low query latency budgets (less than 4ms)
- Requires more than 30% of the dataset size in memory for graph indexing

## Technical Details

SPANN is an on-disk cluster-based index that stores clusters on disk and maintains a small graph in memory to index the nearest clusters. The system is designed for applications requiring billion-scale vector search with memory efficiency.

## Research

Published by Microsoft Research, SPANN represents a significant advancement in disk-based vector indexing technologies and serves as a benchmark for hybrid vector search systems.