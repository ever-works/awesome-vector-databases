## Overview

Haystack enables scalable RAG for LLM applications through composable pipelines handling ingestion, retrieval, and generation.

## Key RAG Features

- **Chunking**: Semantic, fixed-size, recursive splitters with overlap
- **Retrieval**: Hybrid (dense/sparse), MMR diversity, multi-query
- **Vector Store Integrations**: Pinecone, Weaviate, Elasticsearch, FAISS, Milvus, Qdrant
- **Reranking & Post-Processing**: Cross-encoders, reciprocal rank fusion

## Use Cases

- Knowledge retrieval for chatbots
- Enterprise search over docs
- Multi-modal RAG agents

## Comparisons

| Aspect | LangChain | LlamaIndex | Haystack |
|--------|-----------|------------|----------|
| Modularity | Chains/Agents | Data-focused indexes | Pipeline nodes |
| Vector Stores | 100+ loaders | Strong indexing | Optimized retrievers |
| Maturity | Broad ecosystem | Rapid iteration | Production pipelines |

## Pricing

Free open-source (Apache 2.0). Enterprise via deepset Cloud.