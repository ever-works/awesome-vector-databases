## Overview

BGE-reranker-v2-m3 is an open-source multilingual reranking model from the Beijing Academy of Artificial Intelligence (BAAI) using transformer-based cross-encoder architecture designed specifically for reranking tasks.

## Features

- Under 600 million parameters for efficient deployment
- Cross-encoder architecture for accurate relevance scoring
- Multilingual support across many languages
- Open-source under Apache 2.0 license
- Can run on consumer GPUs
- Direct similarity output without requiring embeddings

## Technical Details

- Full-attention over input pairs for maximum accuracy
- Takes question and document as input
- Outputs similarity scores directly
- More accurate than bi-encoders (embedding models)
- More time-consuming than embedding models (trade-off for accuracy)

## Use Cases

- Re-ranking top-k documents from embedding models
- Improving RAG system accuracy
- Two-stage retrieval pipelines
- Question answering systems
- Document relevance scoring

## Performance

Strong Mean Reciprocal Rank (MRR) scores, often achieving results close to top commercial models while being open-source and self-hostable.