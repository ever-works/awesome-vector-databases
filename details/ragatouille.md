## Overview

RAGatouille bridges the gap between state-of-the-art retrieval research and RAG applications, focusing on making ColBERT simple to use. It's a Python library designed to simplify the integration and training of state-of-the-art late-interaction retrieval methods, particularly ColBERT, within RAG pipelines with a modular and user-friendly interface.

## ColBERT Retrieval Method

ColBERT is a fast and accurate retrieval model, enabling scalable BERT-based search over large text collections in tens of milliseconds. While a regular embedding model stores a single vector for each document, ColBERT provides a list of vectors showing how each token in the query matches up with each token in the document.

## Key Features

### Zero-Shot Performance

ColBERT pretrained models are particularly good at generalisation, and ColBERTv2 has repeatedly been shown to be extremely strong at zero-shot retrieval in new domains.

### Dual Functionality

RAGatouille lets you use ColBERT and other SOTA retrieval models in your RAG pipeline, and you can use it to either:
- Run inference on ColBERT
- Train/fine-tune models

## Use Cases

RAGatouille supports two main approaches:
- **Direct retrieval**: Building ColBERT indexes for efficient search
- **Reranking**: Run retrieval against some other index (regular embedding model or full-text search) and then re-rank the results using ColBERT

## Pricing

Free and open-source under MIT License.