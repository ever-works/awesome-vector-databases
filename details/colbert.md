## Overview

ColBERT (Contextualized Late Interaction over BERT) introduces a late interaction architecture that independently encodes queries and documents using BERT, then employs a powerful interaction step to model fine-grained similarity.

## Multi-Vector Representation

Unlike single-vector models, ColBERT produces multi-vector representations at the granularity of each token:
- Generates dense vector representations for each token in a query or document
- Creates a bag of contextualized embeddings for queries and documents
- Each token gets its own contextualized embedding vector

## Late Interaction Mechanism

ColBERT computes relevance scores via late interaction:
1. Find maximum cosine similarity (MaxSim) of each query vector with all document vectors
2. Combine outputs via summation
3. This allows rich semantic matching while remaining efficient

## Key Advantages

- **Contextually Rich**: Surpasses single-vector representation models in quality
- **Scalable**: Efficient computation for large corpora
- **Fine-Grained Matching**: Token-level interactions capture subtle semantic relationships

## Trade-offs

**Storage Requirements**: Requires an embedding for each token, resulting in significantly more storage than single-vector models. However, token embeddings can be stored at lower dimensions and quantization levels to reduce costs.

## Recent Extensions

- **ColPali**: Multimodal late interaction for visual documents
- **ColQwen**: Vision language model variant
- **Video-ColBERT**: Text-to-video retrieval

## Performance

ColBERT achieves state-of-the-art results on passage retrieval benchmarks (SIGIR'20, TACL'21, NeurIPS'21, NAACL'22, CIKM'22, ACL'23, EMNLP'23).

## Use Cases

- Passage retrieval
- Document search
- Question answering
- Semantic search with high precision requirements

## Integrations

- Qdrant (via FastEmbed)
- Available through various vector database platforms

## Pricing

Free and open-source, available on GitHub.