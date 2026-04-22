## Overview

LlamaIndex builds LLM apps with advanced data handling, vector integrations, and agentic capabilities.

## Vector Integration

40+ vector stores including Qdrant:

```python
from llama_index.vector_stores.qdrant import QdrantVectorStore
from llama_index.embeddings.openai import OpenAIEmbedding

vector_store = QdrantVectorStore(...) 
```

## Features

- **Tool Calling**: Query engines as tools for agents
- **Memory**: Chat memory, vector retriever memory
- **Retrieval**: Hybrid search, reranking, multi-retriever fusion

## Use Cases

- Knowledge chatbots
- RAG agents
- Multi-document QA agents

## Comparisons

**LlamaIndex vs LangChain**:

| Feature | LlamaIndex | LangChain |
|---------|------------|-----------|
| Focus | RAG/data pipelines | Chains/agents |
| Vector Stores | 40+ | 50+ |
| Best For | Data connectors | Orchestration |

## Pricing

Open-source (MIT). LlamaCloud paid.