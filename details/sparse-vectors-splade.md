## Overview

Sparse vectors, particularly SPLADE (Sparse Lexical and Expansion Model), represent text using learned sparse representations that are both interpretable and effective for retrieval tasks.

## What are Sparse Vectors?

Unlike dense vectors (fixed-size, continuous values), sparse vectors:
- High-dimensional (vocabulary size)
- Most values are zero
- Non-zero values indicate term importance
- Interpretable (can see which terms matter)

## SPLADE Approach

**Key Innovation**: Uses neural models to learn which terms are important, creating sparse vectors that:
- Expand queries with relevant terms
- Weight terms by importance
- Maintain interpretability
- Enable efficient inverted index storage

## Advantages

- **Interpretability**: Can see which terms drive matches
- **Efficiency**: Sparse structure enables fast search
- **Term Expansion**: Learns to add relevant synonyms
- **Exact Match**: Still captures keyword matching
- **Compatibility**: Works with inverted indexes

## Comparison to Dense Vectors

**Dense Vectors**:
- Fixed size (e.g., 768 dims)
- All values non-zero
- Black box
- Require special indexes (HNSW)

**Sparse Vectors**:
- Variable size (30k+ dims)
- Mostly zeros
- Interpretable
- Use inverted indexes

## Use Cases

- Hybrid search systems
- Explainable retrieval
- Legal/compliance search (auditability)
- Domain-specific search
- Multi-language retrieval

## Database Support

- Qdrant (native sparse vector support)
- Weaviate
- Elasticsearch
- OpenSearch

## Performance

Often competitive with or better than dense retrieval on out-of-domain queries, while maintaining interpretability and efficiency.

## Pricing

SPLADE models available open-source on Hugging Face.