## Overview

MS MARCO Cross-Encoder models are widely used reranker models trained on the MS MARCO dataset for semantic search applications. The most popular variant is cross-encoder/ms-marco-MiniLM-L-6-v2.

## How Cross-Encoders Work

Cross-encoders calculate a similarity score given pairs of texts, processing both the query and document together through every transformer layer. This allows attention to model their interaction directly, providing superior performance compared to bi-encoder (Sentence Transformer) models.

## Architecture

A cross-encoder takes a query–document pair as a single input sequence — [CLS] query [SEP] document [SEP] — and outputs a scalar relevance score.

## Two-Stage Retrieval Pipeline

The recommended approach is:
1. **Stage 1 (Bi-encoder)**: Fast retrieval of top-20 candidates
2. **Stage 2 (Cross-encoder)**: Score each query–chunk pair jointly, return top-3 to the LLM

This balances speed and accuracy, as cross-encoders are slower than sentence transformers but provide higher quality ranking.

## Performance

Models trained on the MS MARCO dataset are very effective as rerankers for search systems, providing high accuracy and deep semantic understanding essential in reranking tasks.

## Output

MS MARCO models return logits rather than normalized scores, though they can be configured to return scores between 0 and 1.

## Use Cases

- Re-ranking search results
- RAG pipeline optimization
- Question-answering systems
- Document retrieval
- Semantic search

## Available Models

- cross-encoder/ms-marco-TinyBERT-L-2-v2
- cross-encoder/ms-marco-MiniLM-L-6-v2 (most popular)
- cross-encoder/ms-marco-MiniLM-L-12-v2
- Available on Hugging Face and Sentence Transformers

## Pricing

Free and open-source models available through Sentence Transformers.