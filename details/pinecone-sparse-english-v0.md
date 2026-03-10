## Overview

pinecone-sparse-english-v0 is a learned sparse embedding model built on the innovations of the DeepImpact architecture, estimating lexical importance of tokens by leveraging their context.

## Performance

- Outperforms BM25 by up to 44% (average 23%) on TREC Deep Learning Tracks
- Measured by normalized discounted cumulative gain (NDCG)@10
- Superior keyword matching with contextual understanding
- Optimized for English language retrieval

## Technical Approach

- Based on DeepImpact architecture
- Context-aware token importance estimation
- Learned sparse representations
- Unlike BM25, leverages semantic context not just term frequency

## Hybrid Search Performance

- Combined with dense retrieval and reranking (cascading retrieval)
- Achieves up to 48% better performance than sparse or dense alone
- Optimal for precision-critical applications

## Integration

- Native Pinecone Inference API support
- Sparse index compatibility
- Works with Pinecone Text Client
- Seamless hybrid search integration

## Use Cases

- High-precision keyword search
- Hybrid semantic + lexical search
- Domain-specific retrieval requiring exact matches
- Cascading retrieval pipelines
- Enterprise search applications

## Pricing

Included with Pinecone API usage, priced per inference call