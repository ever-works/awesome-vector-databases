## Overview

Cascading retrieval is an advanced approach that combines dense retrieval, sparse retrieval, and reranking in a multi-stage pipeline, achieving significantly better performance than any single method alone.

## Architecture

### Stage 1: Initial Retrieval
- Use both dense and sparse vectors
- Retrieve larger candidate set
- Combine semantic and lexical matching

### Stage 2: Reranking
- Apply cross-encoder reranker
- Score candidates more accurately
- Select final top-k results

## Performance Benefits

- Up to 48% better performance vs. sparse or dense alone
- Improved precision at top-k
- Better handling of diverse query types
- More robust retrieval overall

## Components

1. **Dense Retrieval**: Semantic similarity via embeddings
2. **Sparse Retrieval**: Keyword matching (BM25 or learned sparse)
3. **Reranking**: Cross-encoder scoring for accuracy

## Implementation

- Supported in Pinecone with hybrid search + reranking
- Configurable stage parameters
- Flexible component selection
- Production-ready pipeline

## Use Cases

- High-accuracy RAG systems
- Enterprise search applications
- Question answering platforms
- Document retrieval systems
- Precision-critical applications

## Trade-offs

- Higher latency than single-stage
- Increased computational cost
- Better accuracy justifies overhead
- Configurable for speed/accuracy balance

## Best Practices

- Tune candidate set size
- Select appropriate reranker
- Balance sparse/dense weights
- Monitor end-to-end latency
- A/B test configurations