## Overview

Vanna AI is a framework for accurate text-to-SQL generation via LLMs using Agentic Retrieval-Augmented Generation (RAG). It enables users to chat with their SQL databases using natural language, automatically generating and executing SQL queries.

## How It Works

Vanna operates in two steps:

1. **Train**: Build a RAG model on your data by storing database schema, documentation, and question-SQL pairs in a vector store
2. **Ask**: Ask questions in natural language, which retrieves the most relevant context to help generate accurate SQL queries

## Vector Database Support

Vanna supports multiple vector databases:

- **ChromaDB**: Default vector store with ChromaDB_VectorStore implementation
- **Milvus**: World's most advanced open-source vector database
- **Qdrant**: High-performance vector search
- **Custom**: Extensible architecture supports any vector database

## Architecture Components

- **Vector Store**: Stores embeddings of schema, documentation, and example queries
- **Embedder**: Generates vector embeddings from text
- **LLM**: Multiple providers supported (OpenAI, Anthropic, Google Gemini, Ollama, AWS Bedrock)
- **Database Connector**: Connects to any SQL database

## Key Features

- Natural language to SQL translation
- Automatic query execution
- Support for multiple LLMs and vector databases
- Extensible framework for customization
- Integration with popular SQL databases

## Use Cases

- Business intelligence querying
- Data exploration without SQL knowledge
- Automated reporting
- Database Q&A systems