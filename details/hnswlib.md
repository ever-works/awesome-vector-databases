## Overview

HNSWlib is an open-source C++ and Python library implementing the Hierarchical Navigable Small World (HNSW) algorithm for fast approximate nearest neighbor search. Provides header-only implementation for easy integration.

## Key Features

- **Header-Only**: Easy C++ integration without complex build systems
- **Incremental Construction**: Full support for adding elements dynamically
- **Element Updates**: Update vectors in existing index
- **Element Deletion**: Mark elements as deleted
- **Python Support**: Python bindings with pickle support
- **Low Memory Footprint**: Significantly less memory than alternatives
- **Fast Build Time**: Quick index construction

## Performance

- **10x faster** than Annoy for similar accuracy
- Excellent scalability for high-dimensional embeddings
- Efficient query performance
- Production-proven at Spotify and other companies

## Technical Capabilities

- Dynamic index updates
- Concurrent queries (read-only mode)
- Multiple distance metrics (L2, Inner Product, Cosine)
- Configurable graph parameters
- Efficient serialization

## Spotify Adoption

Since 2018, many Spotify teams have experimented with hnswlib:
- Tenfold speed increase over Annoy
- Useful for higher-dimensional embeddings
- Scaled to production use cases
- Led to development of Voyager (successor library by Spotify)

## Python Interface

Simple Python API:
- Create index
- Add items
- Query nearest neighbors
- Save/load index
- Pickle support

## Installation

### Python
```bash
pip install hnswlib
```

### C++
Header-only, just include the headers.

## Use Cases

- Recommendation systems
- Semantic search
- Image similarity
- Content discovery
- Embedding-based retrieval
- Real-time ANN queries

## Pricing

Free and open-source under Apache 2.0 license. No licensing costs.