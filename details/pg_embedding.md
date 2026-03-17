## Overview

The pg_embedding extension enables using the Hierarchical Navigable Small World (HNSW) algorithm for vector similarity search in PostgreSQL. Developed by Neon, this extension provides significantly faster performance than traditional vector indexing methods.

## Key Features

- **HNSW Algorithm**: Implements the Hierarchical Navigable Small World algorithm for efficient approximate nearest neighbor search
- **High Performance**: Delivers 5-30x faster search performance compared to pgvector's IVFFlat indexing for the same recall levels
- **Graph-Based Search**: Uses graph-based approximate nearest neighbor search for superior speed and accuracy
- **PostgreSQL Native**: Seamlessly integrates with PostgreSQL as an extension
- **LangChain Integration**: Works with LangChain's PGEmbedding vectorstore for building AI applications

## Performance

The pg_embedding extension brings 20x the speed for 99% accuracy to graph-based approximate nearest neighbor search. It significantly outperforms pgvector's IVFFlat index in both speed and accuracy for most use cases.

## Installation

The extension can be added to PostgreSQL with the command:
```sql
CREATE EXTENSION embedding;
```

## Use Cases

- Semantic search applications
- RAG (Retrieval Augmented Generation) systems
- Recommendation engines
- Similarity-based search in AI applications
- High-performance vector search in PostgreSQL databases

## Considerations

While HNSW typically provides better speed and accuracy than IVFFlat, it may consume more memory. For strict memory-constrained environments, IVFFlat might be more suitable despite the performance trade-offs.