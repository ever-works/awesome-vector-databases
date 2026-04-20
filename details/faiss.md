# FAISS

**FAISS (Facebook AI Similarity Search)** is an open-source library for efficient similarity search and clustering of dense vectors, developed by Facebook/Meta. It is widely used for powering vector search engines and databases, especially in applications requiring high speed and scalability.

[Visit Website](https://faiss.ai/)

## Features
- **Efficient Similarity Search and Clustering:** Handles dense vectors of any size, including sets that do not fit in RAM.
- **Multiple Distance Metrics:** Supports Euclidean (L2), maximum inner product, and limited support for other metrics (L1, Linf).
- **k-Nearest Neighbors:** Returns not only the single nearest neighbor but also the k-nearest neighbors.
- **Batch Processing:** Can search several vectors at a time for faster performance.
- **Precision-Speed Tradeoff:** Allows trading precision for speed or reduced memory usage (approximate search).
- **Range Search:** Can return all elements within a given radius of the query point.
- **Disk-Based Indexing:** Option to store indices on disk rather than RAM.
- **Binary Vector Indexing:** Supports indexing binary as well as floating-point vectors.
- **Predicate Filtering:** Can ignore a subset of index vectors via predicates on vector IDs.
- **C++ Core with Python Wrappers:** Written in C++ with full Python API wrappers.
- **GPU Acceleration:** Many algorithms are implemented to run on GPUs for high-speed, billion-scale search.
- **Extensive Research Backing:** Implements numerous state-of-the-art algorithms and quantization methods from academic research (e.g., Inverted File, Product Quantization, IVFADC, HNSW, NSG, Residual Quantization, etc.).
- **Parameter Tuning and Evaluation Tools:** Includes supporting code for parameter tuning and evaluation.
- **Open Source:** Freely available under an open-source license.

## Installation
- Install via Conda:
  - CPU: `conda install -c pytorch faiss-cpu`
  - GPU: `conda install -c pytorch faiss-gpu`

## Pricing
- **Free and open-source**