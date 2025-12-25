# Product-Quantization

**Category:** SDKs & Libraries  
**Slug:** `product-quantization`  
**Source:** https://github.com/jatin7gupta/Product-Quantization

## Overview

Product-Quantization is a Python-based implementation of product quantization (PQ) for approximate nearest neighbor (ANN) search, combined with an inverted multi-index structure. It targets scalable vector search on high-dimensional data, such as SIFT and GIST descriptors.

## Features

- **Product Quantization for n-dimensional data**  
  - Decomposes the original vector space into a Cartesian product of multiple low-dimensional subspaces.  
  - Quantizes each subspace separately to generate compact codes.  
  - Represents each vector as a short code made from subspace quantization indices.

- **Approximate Distance Computation**  
  - Efficient estimation of L1 (Manhattan) distance between vectors using their PQ codes.  
  - Supports an asymmetric distance computation variant (vector-to-code) to improve search precision.

- **Inverted Multi-Index Structure**  
  - Implements an inverted multi-index for organizing PQ codes.  
  - Designed to improve efficiency and scalability of ANN search over large datasets.

- **Scalable Vector Search**  
  - Architecture suitable for building scalable vector search engines.  
  - Approach validated in experiments on very large datasets (e.g., billions of vectors, as referenced in included documentation PDFs).

- **Reference Materials & Examples**  
  - `In_Multi-Index.pdf`: documentation/reference on the inverted multi-index structure.  
  - `PQ NN.pdf`: documentation/reference on product quantization for nearest neighbor search.  
  - `demo.py`: example script showing how to run the PQ-based ANN search.  
  - `toy_example/`: small-scale example setup for experimentation.  
  - `Test/`, `test.py`: testing-related code for validating behavior.  
  - `submission.py`: likely a task/competition-oriented wrapper (e.g., for evaluation pipelines).  
  - `requirements.txt`: lists Python dependencies needed to run the project.

## Technology

- **Language:** Python (inferred from `.py` scripts).  
- **Distance metric:** L1 (Manhattan) distance in PQ space.  
- **Use cases:** High-dimensional ANN search (e.g., image descriptors like SIFT and GIST), components for custom vector databases or search engines.

## Pricing

- Not applicable. This is an open-source GitHub repository; no pricing information is provided.