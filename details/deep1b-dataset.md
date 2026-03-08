## Overview

Deep1B (DEEP1B) is a collection of one billion image embeddings compressed to 96 dimensions. This dataset provides a large-scale, real-world proxy for testing distributed systems and GPU-accelerated search.

## Dataset Characteristics

- **Size**: 1 billion vectors
- **Dimensions**: 96-dimensional compressed embeddings
- **Source**: Deep learning image features
- **Type**: Neural network-generated embeddings

## Key Features

- Compressed dimensionality (96D) compared to raw SIFT features
- Reflects modern deep learning embedding characteristics
- Suitable for testing neural embedding search systems
- Real-world distribution of learned features

## Significance

Deep1B is particularly valuable for:
- Evaluating modern embedding-based search systems
- Testing distributed vector databases
- Benchmarking GPU-accelerated vector search
- Assessing performance with neural embeddings vs. hand-crafted features

## Comparison with SIFT1B

While SIFT1B uses hand-crafted 128D features, Deep1B uses learned 96D embeddings, making it more representative of modern AI applications that use neural network embeddings.

## Dataset Access

Available for download from http://corpus-texmex.irisa.fr/
Recommend using Axel for faster downloads of large-scale datasets.

## Applications

- Neural embedding search evaluation
- Deep learning-based retrieval systems
- Modern vector database benchmarking
- Distributed search system testing