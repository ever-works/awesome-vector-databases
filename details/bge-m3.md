## Overview

BGE-M3 stands for Multi-Functionality, Multi-Linguality, and Multi-Granularity. It is a groundbreaking embedding model that can simultaneously perform three common retrieval functionalities in a single model.

## Three Retrieval Methods

### 1. Dense Retrieval
Uses the normalized hidden state of the [CLS] token as the dense embedding for semantic similarity search.

### 2. Sparse Retrieval
Generates sparse vectors (vocabulary-sized with mostly zeros) calculating weights only for tokens present in the text, similar to BM25 but learned.

### 3. Multi-Vector Retrieval (ColBERT-style)
Uses multiple vectors to represent text, enabling fine-grained similarity matching at the token level.

## Key Features

- **Multilingual**: Supports 100+ languages
- **Multi-Granularity**: Handles inputs from short sentences to long documents (up to 8192 tokens)
- **Hybrid Ranking**: Combines multiple retrieval methods for improved accuracy
- **Self-Knowledge Distillation**: Trained using advanced distillation techniques

## Recommended Pipeline

The optimal setup is hybrid retrieval + re-ranking:
1. Use dense or sparse retrieval to get candidate results
2. Rerank using weighted combination of dense, sparse, and multi-vector scores
3. Apply BGE reranker for final ranking

## Performance

On the MLDR test set (13-language long document retrieval):
- Sparse retrieval achieved ~10 NDCG@10 points higher than dense mode
- Dense+sparse hybrid provided further gains
- Strong performance across diverse benchmarks

## Platform Support

- Hugging Face Transformers
- NVIDIA NIM
- DeepInfra
- Ollama
- Vespa and Milvus for hybrid retrieval

## Use Cases

- Multilingual semantic search
- Hybrid search combining keyword and semantic matching
- Long document retrieval
- Cross-lingual information retrieval
- RAG applications requiring multiple retrieval strategies

## Pricing

Free and open-source. Available through various commercial API providers with usage-based pricing.