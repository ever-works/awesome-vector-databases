## Overview

LangChain enables developers to build context-aware LLM applications through composable chains, extensive integrations, and agentic capabilities.

## Vector Integration

Native support for Qdrant, Chroma, FAISS, Pinecone, Weaviate, and 50+ vector stores:

```python
from langchain_community.vectorstores import Qdrant
from langchain_openai import OpenAIEmbeddings

embeddings = OpenAIEmbeddings()
qdrant = Qdrant.from_documents(documents, embeddings, path=":memory:")
retriever = qdrant.as_retriever()
```

## Features

- **Tool Calling**: LCEL for structured function calling and parallel tool execution
- **Memory**: ConversationBufferWindowMemory, EntityMemory, VectorStoreRetrieverMemory for persistent state
- **Agents**: ReAct, Plan-and-Execute agents with toolkits

## Use Cases

- Stateful chatbots with conversation history
- Autonomous agents for multi-step tasks
- RAG-enhanced knowledge retrieval agents

## Comparisons

**LangChain vs LlamaIndex**:

| Feature | LangChain | LlamaIndex |
|---------|-----------|------------|
| Primary Focus | Chains, agents, tools | RAG indexing, query engines |
| Vector Support | 50+ stores | 40+ data connectors |
| Best For | Complex orchestration | Data-heavy RAG pipelines |

## Pricing

Open-source (MIT). LangSmith/LangGraph have paid tiers.