## Overview

RAGatouille provides ColBERT-style retrieval for superior RAG performance in LLM pipelines, emphasizing late-interaction scoring over embeddings.

## Key RAG Features

- **Chunking**: Any preprocessor (LangChain loaders compatible)
- **Retrieval**: Multi-vector token embeddings, max-sim scoring
- **Vector Store Integrations**: FAISS (via HuggingFace), custom indexes
- **Reranking**: Native token-level reranker

## Use Cases

- Precision-critical QA systems
- Domain-adapted retrieval
- Hybrid retriever augmentation

## Comparisons

| Aspect | LangChain | LlamaIndex | RAGatouille |
|--------|-----------|------------|-------------|
| Focus | Full orchestration | Indexing | Retrieval precision |
| Retrieval | Bi-encoder | Embed-based | Late-interaction |
| Ease | Modular | Simple | Specialized |

## Pricing

Free open-source (MIT).