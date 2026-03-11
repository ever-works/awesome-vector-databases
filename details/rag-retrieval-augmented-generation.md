## Overview

RAG (Retrieval-Augmented Generation) enhances LLMs by retrieving relevant information from external knowledge bases before generating responses.

## How RAG Works

### 1. Indexing Phase
- Split documents into chunks
- Generate embeddings
- Store in vector database

### 2. Retrieval Phase
- Convert query to embedding
- Search vector database
- Retrieve top-k relevant chunks

### 3. Generation Phase
- Combine query + retrieved context
- Send to LLM
- Generate grounded response

## Benefits

- **Reduces Hallucinations**: Grounds responses in facts
- **Current Information**: No retraining needed
- **Citations**: Can reference sources
- **Domain Expertise**: Access specialized knowledge
- **Cost-Effective**: vs fine-tuning LLMs

## Components

- **Document Store**: Original documents
- **Vector Database**: Embedded chunks
- **Embedding Model**: Text to vectors
- **LLM**: Response generation
- **Orchestration**: Pipeline management

## Best Practices

- Quality chunking strategies
- Good embedding models
- Hybrid search (keyword + semantic)
- Reranking for precision
- Contextual retrieval techniques

## Popular Frameworks

- LangChain
- LlamaIndex
- Haystack
- Semantic Kernel

## Use Cases

- Customer support chatbots
- Document Q&A
- Knowledge management
- Research assistants
- Internal documentation

## Pricing

Technique, costs from vector DB + LLM + embeddings.