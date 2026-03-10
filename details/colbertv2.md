## Overview

ColBERTv2 (Contextual Late Interactions BERT) is an advanced bi-encoder that represents text in multi-vector embeddings at the token level, introducing a novel late interaction mechanism for efficient and precise ranking.

## How It Works

- Each token gets its own vector embedding
- Encodes passages into matrices of token-level embeddings
- Encodes queries into separate matrices
- Uses scalable MaxSim operators for similarity
- Late interaction compares vectors at final stage

## Improvements Over ColBERT v1

- **Denoised Supervision**: Distillation from larger teacher models
- **Hard Negative Mining**: Improved training with challenging examples
- **Reduced Memory**: Addresses original's huge storage requirements
- **Better Quality**: Enhanced retrieval accuracy
- **Improved Efficiency**: Optimized for production deployment

## Technical Architecture

- Multi-vector representation per document
- Token-level granularity
- Late interaction scoring
- MaxSim aggregation
- Efficient indexing strategies

## Advantages

- Captures complex query semantics
- More accurate than single-vector bi-encoders
- Handles nuanced information needs
- Scalable to large collections
- Fine-grained matching capabilities

## Database Support (2026)

- Weaviate 1.29+ (multi-vector embeddings)
- Qdrant with FastEmbed
- Vespa with native ColBERT embedder
- Milvus with Array of Structs
- VectorChord with MaxSim operators

## Use Cases

- Precision-critical search
- Complex question answering
- Long-document retrieval
- Multi-hop reasoning
- Academic paper search

## Performance

Significant advancement over traditional bi-encoder models, with multi-embedding representations clearly capturing complex queries for more accurate retrievals.

## Pricing

Open-source model, self-hostable or via API providers