## Overview

VectorDB is a minimal Python package for storing and retrieving text using chunking, embeddings, and vector search. Designed and used by Kagi Search to power AI features with optimal performance.

## Key Features

- **Simple and Lightweight**: Minimal dependencies and straightforward API
- **Fully Local**: All operations handled locally including embeddings and search
- **Performance Optimized**: Automatically selects best algorithm based on data size
- **Low Latency**: Optimized for fast query responses
- **Small Memory Footprint**: Efficient resource usage
- **End-to-End Solution**: Complete package from chunking to retrieval

## Automatic Algorithm Selection

VectorDB intelligently chooses the best approach:
- **Faiss**: For low number of chunks (<4000)
- **MRPT**: For high number of chunks (≥4000)

This ensures maximum performance across different use cases without manual configuration.

## Technical Capabilities

- Text chunking and preprocessing
- Embedding generation (local)
- Vector indexing
- Similarity search
- Result retrieval and ranking

## Production Use

Powers AI features inside Kagi Search, demonstrating:
- Production-ready stability
- Real-world performance at scale
- Reliability for user-facing features

## Use Cases

- Semantic search in applications
- Document retrieval systems
- Question answering
- Context retrieval for LLMs
- Content recommendation
- Knowledge base search

## Installation

Available via PyPI:
```bash
pip install vectordb
```

## API

Simple, intuitive Python API for:
- Creating vector stores
- Adding documents
- Querying for similar content
- Managing embeddings

## Integration

Easy integration with:
- Language models (OpenAI, local models)
- Python applications
- Web services
- CLI tools

## Design Philosophy

- **Simplicity**: Easy to understand and use
- **Local-First**: No external dependencies for core functionality
- **Performance**: Optimized for speed and efficiency
- **Transparency**: Clear operations without hidden complexity

## Repository

- GitHub: kagisearch/vectordb
- PyPI: vectordb
- Documentation: In repository README
- Active maintenance by Kagi Search team

## Comparison to Alternatives

### vs. Heavy Solutions
- Much lighter weight
- Faster startup time
- Lower resource usage
- Simpler deployment

### vs. External Services
- No network latency
- Complete data privacy
- No API costs
- Offline capable

## Pricing

Free and open-source. No licensing costs. Available on GitHub under permissive license.