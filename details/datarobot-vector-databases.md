---
name: DataRobot Vector Databases
slug: datarobot-vector-databases
url: https://docs.datarobot.com/en/docs/api/reference/sdk/CHANGES.html
vendor: DataRobot
category: managed-vector-databases
featured: true
images:
  - https://www.datarobot.com/wp-content/uploads/2023/06/genai-hero.png
  - https://www.datarobot.com/wp-content/uploads/2024/01/GenAI-BG.jpg
logo: https://www.datarobot.com/wp-content/uploads/2024/01/datarobot-logo.svg
labels:
  - vector-databases
  - rag
  - managed-service
---

## Overview

DataRobot Vector Databases provide FAISS-based internal vector stores and managed connections to external vector databases. They are integrated into the DataRobot AI platform to support retrieval-augmented generation (RAG) and other embedding-based AI workloads.

The feature focuses on creating and configuring vector databases, managing versions, and registering and deploying these databases as part of production AI systems.

## Features

### Vector database types
- **Internal FAISS-based vector databases** managed directly inside DataRobot.
- **External vector database connections**, including:
  - Pinecone
  - Elasticsearch
  - Milvus

### Creation and configuration
- Create new internal vector databases within the DataRobot platform.
- Configure connection details for supported external vector database providers.
- Associate vector databases with AI projects and deployments.

### Data sources and ingestion
- Add **internal data sources** (data already within DataRobot) to internal vector databases.
- Add and manage **external data sources** as inputs to vector databases.
- Configure ingestion and update behavior for connected databases (where supported by the underlying system).

### Versioning and lifecycle management
- **Versioning for internal vector databases**, allowing tracking and promotion of specific versions.
- **Versioning for connected / external databases**, capturing versions of configurations or snapshots as supported.
- Manage multiple versions for experimentation, testing, and rollback.

### Registration and deployment
- Register vector databases as reusable assets within the DataRobot platform.
- Deploy vector databases into production environments as part of AI applications.
- Use deployed vector databases as a retrieval layer for models and generative pipelines.

### RAG and AI use cases
- Power **retrieval-augmented generation (RAG)** workflows by providing similarity search over embedded documents.
- Support other **embedding-based AI use cases**, such as semantic search and recommendation, through the same internal/external vector database abstraction.

## Integrations

- **Internal**: FAISS-based vector store integrated natively with DataRobot.
- **External vector databases**:
  - Pinecone
  - Elasticsearch
  - Milvus

## Pricing

Pricing information is not provided in the available content. Refer to DataRobot’s official pricing or sales materials for details on plans and costs related to vector databases.