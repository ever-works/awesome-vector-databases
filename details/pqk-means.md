## Overview

PQk-means is an efficient clustering method for billion-scale feature vectors that addresses the scalability limitations of traditional k-means clustering. Published at ACM International Conference on Multimedia (ACMMM) in 2017, the method enables clustering of massive datasets on single machines with limited memory.

## How It Works

**Product Quantization Compression**: Input vectors are compressed into short product-quantized (PQ) codes before clustering, dramatically reducing memory requirements

**PQ-Code Domain Operations**: Similar to k-means, PQk-means repeats the assignment and update steps, both of which can be performed directly in the PQ-code domain

**Efficient Processing**: Both assignment and update operations leverage the compressed representation without requiring full vector reconstruction

## Performance Metrics

- Clusters one billion 128D SIFT features with K = 10^5 in 14 hours
- Requires only 32 GB of memory on a single computer
- Competitive accuracy with traditional k-means even using short 32-bit PQ-codes
- Suitable for billion-scale datasets that would be impossible to cluster with standard k-means

## Implementation

PQk-means is available as a Python library designed for efficient clustering of large-scale data. The library provides an easy-to-use interface while maintaining the performance benefits of product quantization.

## Use Cases

- Large-scale image feature clustering
- Dimensionality reduction for billion-scale embeddings
- Building hierarchical indexes for vector databases
- Creating codebooks for product quantization in ANN search

## Availability

The method was developed by Yusuke Matsui, Keisuke Ogaki, Toshihiko Yamasaki, and Kiyoharu Aizawa. Available on arXiv (1709.03708) and as an open-source Python library.