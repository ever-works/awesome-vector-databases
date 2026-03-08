## Overview

ModernBERT Embed is an embedding model trained from ModernBERT-base, bringing the new advances of ModernBERT to embeddings. Trained on the Nomic Embed weakly-supervised and supervised datasets.

## Key Features

- Based on ModernBERT-base with 149M parameters
- Outperforms both nomic-embed-text-v1 and nomic-embed-text-v1.5 on MTEB
- Maximum sequence length of 8192 tokens
- Supports Matryoshka Representation Learning dimensions of 256
- 2 valid output dimensionalities: 768 and 256
- 3x memory reduction with minimal performance loss using dimension 256

## Usage Requirements

This model requires prefixes to be added to the input (similar to Nomic Embed):
- Add `search_query:` prefix to queries
- Add `search_document:` prefix to documents

## Applications

- Semantic search
- Classification
- Clustering
- Reranking tasks

## License

Apache 2.0 licensed - fully commercially permissible

## Requirements

Requires transformers>=4.48.0

## Availability

Available on Hugging Face at `nomic-ai/modernbert-embed-base`