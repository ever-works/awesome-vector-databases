## Overview

IVF_SQ8 is a quantization-based indexing algorithm designed to tackle large-scale similarity search challenges. It combines the Inverted File Index (IVF) structure with 8-bit scalar quantization (SQ8) to achieve faster searches with a much smaller memory footprint.

## How IVF-SQ8 Works

### IVF Component

The dataset is partitioned into clusters using k-means clustering, where each cluster is represented by a centroid. During search, the query vector is compared to centroids to identify the nearest clusters, and only vectors within those clusters are searched.

### SQ8 Quantization

SQ8 uses 8-bit integers instead of the typical 32-bit floating point numbers to store each dimension value of a vector. This 4x reduction in size:

1. Identifies minimum and maximum values within the vector
2. Normalizes vector values to a range between 0 and 1
3. Multiplies by 255 and rounds to nearest integer
4. Stores as 8-bit representation

## Key Benefits

- **4x Memory Reduction**: Compresses vectors from float32 to int8
- **Faster Computation**: Reduced memory usage accelerates distance computations
- **Maintained Accuracy**: Preserves enough precision for fast similarity calculations
- **Scalable**: Handles billion-scale vector datasets efficiently

## Use Cases

- Large-scale image retrieval
- Document similarity search
- Recommendation systems
- High-dimensional vector search with memory constraints

## Trade-offs

- Slight accuracy loss compared to full precision
- Requires training phase for cluster creation
- nlist parameter tuning needed for optimal performance

## Pricing

Available in open-source vector databases like Milvus and FAISS.