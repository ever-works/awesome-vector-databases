## Overview

NV-Embed is a generalist embedding model that enhances the performance of decoder-only LLMs for embedding and retrieval tasks, with various architectural designs and training procedures.

## Performance

Using only publicly available data, NV-Embed achieved:
- Record-high score of 69.32 on MTEB (Massive Text Embedding Benchmark)
- Ranked #1 on MTEB as of May 24, 2024
- Evaluated across 56 tasks

## NVIDIA Llama-based Embedding Models (2026)

NVIDIA has developed several embedding models based on Llama architecture:

### llama-text-embed-v2
- Built on Llama 3.2 1B architecture
- Optimized for high retrieval quality with low-latency inference

### llama-3.2-nv-embedqa-1b-v2
- Dense text embedding model for fixed-length vector representations
- Note: API will be deprecated on 05/18/2026

### llama-embed-nemotron-8b
- Open-weights text embedding model
- Achieves state-of-the-art performance on Multilingual MTEB leaderboard (October 21, 2025)
- Based on meta-llama/Llama-3.1-8B
- Fine-tuned version with bidirectional attention mechanism

## NV-Embed-v2 (October 2025)

- Latest embedding model from NVIDIA
- Fine-tuned from Llama-3.1-8B
- Particularly powerful at understanding multilingual text
- Continues NVIDIA's leadership in embedding model performance

## Key Innovations

- Improved techniques for training LLMs as generalist embedding models
- Decoder-only architecture optimization for embeddings
- Bidirectional attention mechanisms
- Multilingual capabilities

## Applications

- Semantic search
- Retrieval-augmented generation (RAG)
- Multilingual information retrieval
- Cross-lingual tasks
- General-purpose text embedding

## Availability

Available through:
- NVIDIA NIM (NVIDIA Inference Microservices)
- Hugging Face
- Research paper on arXiv