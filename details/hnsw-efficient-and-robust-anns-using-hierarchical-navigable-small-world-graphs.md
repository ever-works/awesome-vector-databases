## Overview

HNSW is a hierarchical graph-based approximate nearest neighbor search algorithm that builds multi-layer navigable small world graphs for efficient similarity search.

## Key Contributions

- Hierarchical multi-layer graph structure with shortcuts across levels
- Logarithmic search complexity in practice
- High recall with low latency on diverse datasets
- Foundation for most production graph-based vector search systems

## Publication

- **Venue**: IEEE TPAMI 2018
- **Authors**: Malkov and Yashunin
- **Abbreviation**: HNSW

## Impact

HNSW became the de facto standard for ANN search in production vector databases and is implemented in nearly all major vector DBMS engines.