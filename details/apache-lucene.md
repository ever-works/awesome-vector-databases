## Overview

Apache Lucene is an open-source information retrieval software library originally written in Java. It is widely used as the foundation for search engines like Apache Solr and Elasticsearch. Lucene supports both traditional lexical (keyword) search and modern vector-based semantic search.

## Vector Search Capabilities

- **HNSW Algorithm**: Implements Hierarchical Navigable Small World Graphs for approximate nearest neighbor (ANN) search
- **KnnFloatVectorField**: Field type for indexing floating-point embedding vectors with configurable similarity functions (e.g., cosine similarity)
- **KnnFloatVectorQuery**: Query type for performing KNN searches on indexed vector fields
- **Default dimension limit**: 1024 dimensions (can be extended via custom KnnVectorsFormat codecs, e.g., HighDimensionKnnVectorsFormat for 1536+ dimensions)
- **Similarity functions**: Supports cosine similarity and other distance metrics via VectorSimilarityFunction
- **Codec customization**: Lucene95Codec with Mode.BEST_SPEED for optimized vector indexing performance

## Index Storage

- **ByteBuffersDirectory**: Keeps index files in heap memory for fast access
- **FSDirectory**: Stores index files on the file system for persistence
- **IndexWriter**: Handles document indexing with configurable analyzers and codecs

## Use Cases

- Semantic search over unstructured data (text, images, video)
- Embedding-based document retrieval with deep learning models (e.g., OpenAI embeddings)
- High-dimensional vector similarity search for AI/ML applications
- Hybrid search combining lexical and semantic relevance

## Pricing

Free and open-source under the Apache License 2.0.