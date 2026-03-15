## Overview

Navigable Small World (NSW) is a graph-based algorithm that finds approximate nearest neighbors in a dataset. By building proximity graphs with both long-range and short-range links, search times are reduced to poly-logarithmic complexity.

## Core Concept

The "small world" property means that most nodes can be reached from any other node through a small number of hops, similar to the "six degrees of separation" concept in social networks.

## Key Features

- **Dual-Range Links**: Combines long-range connections for fast traversal and short-range connections for local refinement
- **Greedy Search**: Navigates from a random entry point toward the query by following nearest neighbors
- **Poly-logarithmic Complexity**: Search time scales as O((log N)^k) where N is dataset size
- **Incremental Construction**: Graph can be built incrementally as data arrives

## How It Works

1. Start from a random entry point in the graph
2. Greedily move to the neighbor closest to the query
3. Continue until reaching a local minimum
4. Return the k-nearest neighbors found

## Evolution to HNSW

NSW evolved into Hierarchical Navigable Small World (HNSW), which adds hierarchical layers to further improve search efficiency and accuracy.

## Advantages

- Fast search with logarithmic complexity
- Good accuracy for approximate search
- Simple greedy search procedure
- Incremental index construction

## Limitations

- If query and seed are far apart in search space, many hops are needed
- No guarantees on search quality
- Potential for hubness problems (some nodes dominate connections)

## Applications

- Approximate nearest neighbor search
- Similarity search in high-dimensional spaces
- Recommendation systems
- Image and document retrieval

## Pricing

Not applicable (algorithmic concept).