# Lossless Compression of Vector IDs for Approximate Nearest Neighbor Search

- **Type:** Research paper
- **Category:** Curated Resource / Research
- **Source:** arXiv
- **Authors:** Daniel Severo, Giuseppe Ottaviano, Matthew Muckley, Karen Ullrich, Matthijs Douze
- **Link:** https://arxiv.org/pdf/2501.10479
- **Code:** https://github.com/facebookresearch/vector_db_id_compression

## Summary

This paper introduces lossless compression schemes for vector identifiers (IDs) and graph links in approximate nearest neighbor (ANN) search systems. While prior work has focused mainly on lossy compression of vectors (embedding quantization), this work targets the often-dominant memory cost of auxiliary indexing data such as vector IDs and edges in inverted file (IVF) and graph-based indices.

The methods exploit the fact that the ordering of IDs inside certain ANN data structures (e.g., within clusters or adjacency lists) is irrelevant, enabling entropy-based, structure-aware compression without affecting search semantics.

## Features

### Problem Addressed
- High RAM usage in ANN indices due to:
  - Storage of large numbers of vector IDs in inverted-file based indices.
  - Storage of neighbor links/edges in graph-based indices.
- Existing focus on **lossy vector compression** (e.g., product quantization) leaves a large portion of index memory unoptimized (IDs and links).
- Need to reduce index size while preserving:
  - Exact ID information (lossless).
  - Search accuracy.
  - Query latency / runtime.

### Proposed Approach
- **Lossless compression of vector IDs and links** in ANN indices.
- Targets two main index families:
  - **Inverted file (IVF) indices:** IDs stored in per-cluster posting lists.
  - **Graph-based indices:** Neighbor IDs stored as edges.
- Leverages structural properties of these indices:
  - **Order invariance:** Within a cluster or adjacency list, the order of IDs does not matter for retrieval.
- Uses advanced entropy coding and data structures:
  - **Asymmetric Numeral Systems (ANS)** for entropy-based encoding.
  - **Wavelet trees** to compactly represent ID sets while supporting needed operations.

### Technical Highlights
- Integrates with standard ANN pipelines where:
  - Vectors are **lossily compressed** (e.g., Product Quantization, QINCo).
  - IDs and/or links are **additionally compressed losslessly**.
- Applicable to:
  - Vector identifiers in IVF indices (cluster posting lists).
  - Link / edge identifiers in graph-based vector indices.
- Exploits properties of existing quantization algorithms to:
  - Sometimes **losslessly compress quantized vector codes themselves**, by capturing sub-optimalities or redundancies in the original quantization.

### Performance and Impact (as reported)
- **Compression ratio:**
  - Up to **7× compression** of vector IDs in some settings.
- **Index size reduction:**
  - Around **30% reduction** in overall index size on **billion-scale datasets**.
- **Quality and speed:**
  - No impact on **search accuracy**.
  - No measurable increase in **search runtime** in the reported experiments.

### Use Cases
- Large-scale vector databases and similarity search engines where:
  - RAM is the primary constraint.
  - ANN indices must fit in memory on a single or small number of machines.
- Systems using:
  - IVF-style indices with compressed vectors.
  - Graph-based ANN indices (e.g., for multimedia retrieval, recommendation, semantic search).

## Category & Tags
- **Category:** Curated resource list / Research paper on ANN and index compression
- **Relevant Topics:**
  - Approximate nearest neighbor (ANN) search
  - Vector databases
  - Lossless compression
  - Entropy coding (ANS)
  - Wavelet trees
  - Inverted file indices (IVF)
  - Graph-based indices
  - Product quantization

## Pricing

- Not applicable (research paper and open-source code).