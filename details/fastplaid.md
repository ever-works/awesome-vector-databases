## Overview

FastPLAID is an optimized implementation of the PLAID (Performance-optimized Late Interaction Driver) index specifically designed for fast ColBERT retrieval. It serves as the default index backend in the PyLate library.

## Key Features

### Performance
- 10x storage compression compared to original PLAID
- Sub-200ms latency for queries
- Optimized for production deployments

### Purpose-Built for ColBERT
FastPLAID is a purpose-built index for fast ColBERT retrieval, specifically optimized for late interaction models that retain all token representations.

## Comparison with Stanford PLAID

FastPLAID is significantly faster than the original Stanford PLAID implementation. While the Stanford PLAID is primarily for research or comparison purposes, FastPLAID is designed for production use with practical optimizations.

## Integration

FastPLAID is seamlessly integrated into PyLate, making it the default choice for users building ColBERT-based retrieval systems. Users can also opt for the original Stanford PLAID implementation if needed for research purposes.

##Implementation Example

```python
from pylate import indexes

index = indexes.PLAID(
    index_folder="pylate-colbert-index",
    index_name="my_documents",
    override=True,  # Use FastPLAID by default
)
```

## Companion Library

For complete, high-performance multi-vector search pipelines, FastPLAID can be paired with pylate-rs, a lightweight Rust-based implementation for production use.

## Use Cases

- Production ColBERT deployments
- Multi-vector retrieval systems
- Late interaction semantic search
- RAG applications requiring token-level matching

## Pricing

Free and open-source as part of PyLate.