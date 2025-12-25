# SOAR

**Brand:** Google Research  
**Category:** Research Papers & Surveys  
**Type:** Vector search algorithm (on top of ScaNN)  
**Source:** [SOAR: New algorithms for even faster vector search with ScaNN](https://research.google/blog/soar-new-algorithms-for-even-faster-vector-search-with-scann/)

![SOAR illustration](https://research.google/static/blog/images/SOAR-New-algorithms/thumbnail_800.png)

## Description
SOAR (Spilling with Orthogonality-Amplified Residuals) is a set of improved algorithms built on top of the ScaNN vector search library. It focuses on accelerating approximate nearest neighbor (ANN) search over large-scale embedding datasets by introducing controlled redundancy and multi-cluster assignment. This design enables faster vector similarity search while keeping index sizes relatively small and preserving key index quality metrics.

## Key Details
- **Domain:** Approximate nearest neighbor (ANN) / vector similarity search
- **Primary use cases:** Large-scale embedding search for ML applications (e.g., image, web, media retrieval; retrieval-augmented generation systems)
- **Publication:** “SOAR: Improved Indexing for Approximate Nearest Neighbor Search” (NeurIPS 2023)
- **Underlying system:** Extends and enhances the ScaNN open-source vector search library

## Features
- **Improved indexing for ANN search**  
  - Introduces a new indexing approach (SOAR) that refines how ScaNN structures and searches large embedding datasets.

- **Controlled redundancy in the vector index**  
  - Adds mathematically designed redundancy to the index to improve search efficiency.  
  - Redundancy is engineered to have minimal impact on overall index size and other index metrics.

- **Multi-cluster assignment**  
  - Assigns vectors to multiple clusters (multi-cluster assignment) to increase the likelihood that true nearest neighbors are retrieved quickly.  
  - Supports faster approximate nearest neighbor retrieval, especially at large scales.

- **Orthogonality-amplified residuals (conceptual)**  
  - Uses residual-based techniques that emphasize orthogonality properties to make redundancy more effective for search.  
  - Designed to complement ScaNN’s existing partitioning and scoring mechanisms.

- **Faster vector search at scale**  
  - Targets large-scale deployments where brute-force search is infeasible.  
  - Aims to reduce latency and computation per query for vector similarity search workloads.

- **Smaller, efficient indexes**  
  - Seeks a balance between added redundancy and compact index representation, keeping index growth modest while improving recall and performance.

- **Integration with ScaNN**  
  - Builds directly on the ScaNN library, which is already widely used and open-sourced.  
  - Can be applied in settings where ScaNN is used for embedding-based retrieval within production ML systems.

## Applications
- Large-scale embedding retrieval for search and recommendation systems.
- Retrieval-augmented generation (RAG) workflows requiring fast ANN lookup. 
- Any ML system that relies on efficient vector similarity search over very large collections of embeddings.

## Pricing
Not applicable. SOAR is presented as a research contribution and algorithmic improvement to the open-source ScaNN library; no pricing information is provided in the source content.