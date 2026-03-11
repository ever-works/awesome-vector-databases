## Overview

Late interaction is a neural ranking paradigm that defers the interaction between query and document representations until the final similarity computation. This enables more expressive matching while maintaining efficiency.

## How It Works

1. **Independent Encoding**: Query and document are encoded separately into token-level embeddings
2. **Storage**: Document embeddings stored in vector database
3. **Query Time**: Interaction computed between query and document tokens
4. **Scoring**: MaxSim or other functions aggregate token interactions

## Key Innovation

Unlike traditional dense retrieval that compresses documents into single vectors, late interaction preserves token-level information, enabling:
- Fine-grained semantic matching
- Better handling of long documents
- More interpretable relevance signals

## Pioneered by ColBERT

ColBERT introduced late interaction to balance:
- **Cross-Encoders**: Highly accurate but slow (encode query-document pairs together)
- **Bi-Encoders**: Fast but less accurate (single vector per document)
- **Late Interaction**: Best of both worlds

## Advantages

- Higher relevance than single-vector approaches
- Much faster than cross-encoders
- Token-level interpretability
- Better for long documents
- Maintains semantic richness

## Use Cases

- Long-document retrieval
- High-precision search applications
- Multi-stage ranking pipelines
- RAG systems requiring high relevance
- Technical documentation search

## Models Using Late Interaction

- **ColBERT**: Original late interaction model
- **Jina ColBERT v2**: Multilingual late interaction
- **ColBERTv2**: Improved version with better efficiency

## Integration in RAG

Typically used as re-ranking stage after initial retrieval with BM25 or dense vectors.

## Performance

Late interaction ranking models deliver high-quality ranking results on large-scale datasets, crucial for production RAG systems.