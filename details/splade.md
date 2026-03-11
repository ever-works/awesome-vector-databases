## Overview

SPLADE (Sparse Lexical and Expansion) is one of the most performant learnable sparse embedding models, using pretrained language models like BERT to enhance sparse vector embeddings.

## How SPLADE Works

### Two Main Mechanisms

1. **Term Weighting**: Weights relevance of different terms
2. **Term Expansion**: Includes alternative but semantically relevant terms beyond original sequence

### Technical Implementation

- Applies MLM (Masked Language Modeling) across all token positions
- Calculates probability each token corresponds to every vocabulary word
- Creates learned sparse vectors with relevance-based weights
- Highly sparse representations

## Key Innovation

SPLADE can **learn term expansions** rather than using rule-based methods, enabling it to discover semantic connections automatically.

## Performance

- Outperforms BM25 in information retrieval
- Competitive with state-of-the-art dense approaches
- Strong results in document classification
- Maintains interpretability of sparse vectors

## Advantages

### vs BM25
- Learned term relationships
- Semantic understanding
- Better recall and precision

### vs Dense Embeddings
- Interpretable weights
- Exact term matching preserved
- Lower storage for very high dimensions
- Explainable relevance

## Use Cases

- Hybrid search systems
- Interpretable retrieval
- Domain-specific search
- RAG systems needing transparency
- Combining with dense vectors

## Integration

- **Qdrant**: FastEmbed SPLADE support
- **Pinecone**: Sparse-dense hybrid search
- **Elasticsearch**: Sparse vector fields
- **BGE-M3**: Includes SPLADE-style sparse retrieval

## Pricing

Open-source models available on HuggingFace. Compute costs for inference.