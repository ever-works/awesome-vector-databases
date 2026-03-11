## Overview

HNSW is a graph-based indexing algorithm that builds a multi-layered structure of navigable small world graphs for efficient approximate nearest neighbor search.

## Key Characteristics

- **Logarithmic complexity**: O(log N) search time
- **Hierarchical layers**: Multiple resolution levels
- **Graph structure**: Navigable small world networks
- **High recall**: 90%+ typical accuracy
- **Fast queries**: Millisecond-range latencies

## How It Works

1. **Build hierarchy**: Create multiple graph layers
2. **Top-down search**: Start at top layer
3. **Navigate graphs**: Move through connected nodes
4. **Refine results**: Zoom into lower layers
5. **Return neighbors**: Bottom layer results

## Parameters

- **M**: Max connections per node (16-48 typical)
- **efConstruction**: Build-time search depth
- **efSearch**: Query-time search depth

## Advantages

- Excellent recall-speed tradeoff
- Scalable to billions of vectors
- Incremental updates supported
- Well-tested and proven

## Used In

- Weaviate
- Qdrant
- Milvus
- pgvectorscale
- HNSWlib
- FAISS
- Elasticsearch

## Pricing

Open algorithm, no licensing.