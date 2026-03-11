## Overview

Product Quantization (PQ) compresses vectors by splitting them into subvectors and quantizing each segment independently, dramatically reducing memory footprint.

## Process

1. Divide vector into m subvectors
2. Cluster each subvector space (k-means)
3. Replace subvectors with centroid IDs
4. Store compressed codes + codebooks
5. Approximate distances using precomputed tables

## Compression

- **8-64x reduction** typical
- Configurable via m and k parameters
- Tradeoff with accuracy

## Variants

- **OPQ**: Optimized with rotation
- **IVFPQ**: Combined with IVF
- **HNSW-PQ**: Graph index with compression

## Used In

- FAISS
- Milvus
- ScaNN
- LanceDB

## Pricing

Open technique.