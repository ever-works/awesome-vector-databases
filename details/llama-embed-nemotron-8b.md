## Overview

llama-embed-nemotron-8b is a versatile text embedding model trained by NVIDIA and optimized for retrieval, reranking, semantic similarity, and classification use cases. It achieves state-of-the-art performance on the Multilingual Massive Text Embedding Benchmark (MMTEB) leaderboard as of October 21, 2025.

## Architecture & Vector Embeddings

The model consists of:
- 32 hidden layers
- Embedding size of 4,096 dimensions
- Global average pooling to compress token information into dense vectors
- Initializes using the weights and architecture of Llama-3.1-8B model
- Replaces causal attention mask with bi-directional attention

## Key Capabilities

### Multilingual and Cross-Lingual

Robust capabilities for multilingual and cross-lingual text retrieval, designed to serve as a foundational component in text-based Retrieval-Augmented Generation (RAG) systems.

### Instruction-Tuned

A universal, instruction-tuned text embedding model designed to generate specialized embeddings for a wide range of tasks, including retrieval, classification, and semantic textual similarity (STS).

## Training Data

The complete dataset consists of 4.3 million samples from a diverse range of corpora:
- Approximately 2.7 million non-synthetic samples from public sources
- 1.6 million synthetic samples

## Performance

Achieved 62% Top-1 accuracy, the highest among all tested embedding models in comparative benchmarks.

## Pricing

Free to use under NVIDIA AI Foundation Models license.