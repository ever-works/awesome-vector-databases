## Overview

Canopy is an open-source Retrieval Augmented Generation (RAG) framework and context engine built on top of the Pinecone vector database. It enables rapid experimentation and development of RAG applications.

**Important Note**: The Canopy team is no longer maintaining this repository. For a managed RAG solution with continued updates, consider Pinecone Assistant.

## Architecture Components

### 1. Knowledge Base
Prepares data for the RAG workflow:
- Automatically chunks text data
- Transforms data into text embeddings
- Upserts embeddings into Pinecone vector database
- Handles data preprocessing and indexing

### 2. Context Engine
Implements the retrieval part of RAG:
- Finds most relevant documents from Pinecone via the Knowledge Base
- Structures documents as context for LLM prompts
- Optimizes context selection for relevance
- Manages context window limitations

### 3. Chat Engine
Implements the complete RAG workflow:
- Understands chat history and context
- Identifies multi-part questions
- Generates multiple relevant queries from single prompts
- Transforms queries into embeddings
- Uses generated context for LLM responses
- Presents highly relevant responses to end users

## Key Features

- **Automatic Chunking**: Intelligent text segmentation
- **Embedding Management**: Handles text-to-vector conversion
- **Chat History**: Maintains conversation context
- **Query Optimization**: Enhances retrieval quality
- **Prompt Engineering**: Built-in optimization for LLM prompts
- **Augmented Generation**: Complete RAG pipeline implementation

## Workflows

### Knowledge Base Creation Flow
1. Users upload documents
2. Documents transformed into vector representations
3. Stored in Pinecone's Vector Database
4. Indexed for efficient retrieval

### Chat Flow
1. Incoming queries and chat history captured
2. Queries optimized for retrieval
3. Knowledge base queried for relevant documents
4. Context generated for LLM
5. LLM generates contextual answer

## Deployment Options

### Canopy Server
- Built on FastAPI, Uvicorn, and Gunicorn
- Exposes Canopy Core library as REST API
- Production-ready deployment
- Easy integration with existing systems

### Library Usage
Integrate Canopy Core library directly into Python applications for maximum control and customization.

## Use Cases

- Question-answering systems over proprietary documents
- Customer support chatbots with knowledge bases
- Document search and retrieval applications
- Enterprise knowledge management systems
- RAG prototyping and experimentation

## Availability

Open-source on GitHub: https://github.com/pinecone-io/canopy

## Note on Maintenance

While the repository is no longer actively maintained, it remains available as a reference implementation and can be forked for custom development.