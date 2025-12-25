# DET-LSH

**Category:** Research Papers & Surveys  
**Brand:** arXiv  
**Source:** [Paper PDF](https://arxiv.org/pdf/2406.10938)  
**Code & Artifacts:** [GitHub – WeiJiuQi/DET-LSH](https://github.com/WeiJiuQi/DET-LSH)

## Overview
DET-LSH is a locality-sensitive hashing (LSH) scheme designed for approximate nearest neighbor (ANN) search in high-dimensional Euclidean spaces. It introduces a Dynamic Encoding Tree (DE-Tree) structure to accelerate both indexing and querying, with a focus on improving indexing efficiency—an aspect often underemphasized in traditional LSH-based methods.

## Key Concepts
- **Approximate Nearest Neighbor (ANN) Search:** Targets efficient retrieval of points whose distances to a query are within a factor \(c\) of the true nearest neighbor distance in high-dimensional spaces.
- **Locality-Sensitive Hashing (LSH):** A hashing framework that increases collision probability for nearby points to enable sublinear-time ANN search.

## Features

### Dynamic Encoding Tree (DE-Tree)
- **Encoding-based index tree** designed specifically for ANN tasks.
- Focuses on **improving indexing efficiency** rather than only query-time optimizations.
- Avoids directly partitioning the raw multi-dimensional space, mitigating performance degradation as dimensionality increases.
- Supports **efficient range queries** based on Euclidean distance.

### DET-LSH Scheme
- Builds **multiple independent DE-Tree indexes** over the data.
- Employs a **novel query strategy** that:
  - Performs **range queries across multiple DE-Trees**.
  - **Reduces the probability of missing exact nearest neighbor points**, thereby improving recall and overall query accuracy.
- Designed as a **general LSH-based framework** that can be used to inspire or implement vector indexing components in vector databases.

### Theoretical Properties
- Provides **probabilistic guarantees on query accuracy**, in line with classical LSH theory.
- Formally analyzed within the approximate nearest neighbor (\(c\)-ANN) framework for Euclidean distance.

### Performance Characteristics
- Targets **high-dimensional Euclidean spaces** where the curse of dimensionality makes exact NN search impractical.
- Experimental results on real-world datasets (as reported in the paper):
  - Up to **6× speedup in indexing time** compared to state-of-the-art LSH-based methods.
  - Up to **2× speedup in query time**.
  - **Higher query accuracy** than competing LSH-based approaches under comparable settings.

## Use Cases
- Designing or optimizing **vector indexing components** in vector databases and search systems.
- High-dimensional ANN search applications in:
  - Databases and data management
  - Information retrieval
  - Data mining
  - Machine learning and embedding-based similarity search

## Publication & Licensing
- **Venue:** PVLDB, Vol. 17, No. 9 (2024), pp. 2241–2254.  
- **DOI:** 10.14778/3665844.3665854  
- **License:** Creative Commons BY-NC-ND 4.0 (non-commercial, no derivatives for the paper text).

## Pricing
- Not applicable. DET-LSH is a **research algorithm** with an academic publication and open-source artifacts rather than a commercial product or service with pricing plans.