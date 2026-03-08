## Overview

NSW (Navigable Small World) is a graph-based algorithm that finds approximate nearest neighbors in a dataset. An NSW is a graph where the vertices represent vectors and the edges are constructed heuristically from the similarity between vectors so that most vectors are reachable from anywhere via a small number of hops.

## How NSW Works

Vector search using Navigable Small World graphs was introduced over the course of several papers from 2011-14. The key idea is that if we build a proximity graph with both long-range and short-range links, search times are reduced to (poly/)logarithmic complexity.

## Search Algorithm

1. Begin at a pre-defined entry point
2. Identify which nearby vertices is closest to the query vector
3. Move to that vertex
4. Repeat greedy-routing search process by identifying nearest neighboring vertices
5. Continue moving from vertex to vertex until local minimum is reached

## Evolution to HNSW

The Hierarchical navigable small world (HNSW) algorithm builds on NSW by combining it with Skip Lists, generating a multi-layer NSW graph that enables logarithmic time complexity for approximate nearest neighbor search.

## Performance Characteristics

Navigable small world models achieve (poly/)logarithmic complexity using greedy routing. The algorithm greedily traverses to connected vertices that are nearer to the query vector.

## Applications

NSW graphs serve as the foundation for many modern vector similarity search systems and are used in production vector databases for efficient approximate nearest neighbor search.