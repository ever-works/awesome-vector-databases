## Overview

SPLADE (Sparse Lexical and Expansion Model) uses a pretrained language model like BERT to identify connections between words/sub-words and enhance sparse vector embeddings for efficient retrieval.

## Features

- Leverages transformer architecture (BERT-based)
- Generates sparse representations of documents and queries
- Enables efficient retrieval with interpretability
- Combines benefits of learned embeddings with sparse representations
- Better than traditional BM25 in many benchmarks
- Explainable results through sparse activations

## Technical Approach

- Uses pretrained language models for term expansion
- Creates sparse vectors with meaningful non-zero dimensions
- Balances performance with efficiency
- Supports hybrid search when combined with dense vectors

## Use Cases

- Information retrieval systems
- Semantic search with interpretability
- Hybrid search architectures
- Document ranking and retrieval
- Question answering systems

## Performance

Recent research validates that hybrid searches using both sparse vectors (SPLADE) and dense vectors surpass traditional BM25 in typical information retrieval evaluation tasks.