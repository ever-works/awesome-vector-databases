## Overview

VectorETL is a powerful and flexible ETL framework designed to streamline the process of extracting data from various sources, transforming it into vector embeddings, and loading these embeddings into a range of vector databases.

## Key Features

- **No-Code Configuration**: Execute end-to-end ETL processes with easily configurable YAML or JSON files
- **Multiple Data Sources**: Extract data from databases, APIs, files, and other sources
- **Embedding Generation**: Transform data into vector embeddings using various embedding models
- **Multiple Vector Database Support**: Load embeddings into Pinecone, Weaviate, Milvus, Chroma, and more
- **Flexible Pipeline**: Customizable ETL pipeline stages
- **Batch Processing**: Efficient processing of large datasets
- **Error Handling**: Robust error handling and retry mechanisms

## Architecture

The framework consists of three main components:

1. **Extractors**: Pull data from various sources
2. **Transformers**: Convert data into vector embeddings
3. **Loaders**: Insert embeddings into vector databases

## Configuration

Configure pipelines using simple YAML or JSON files:

```yaml
source:
  type: csv
  path: /data/documents.csv

transform:
  embedding_model: sentence-transformers/all-MiniLM-L6-v2
  chunk_size: 512

destination:
  type: pinecone
  index: my-index
```

## Supported Sources

- CSV/JSON files
- SQL databases
- REST APIs
- Cloud storage (S3, GCS, Azure)
- Document stores

## Supported Destinations

- Pinecone
- Weaviate
- Milvus
- Qdrant
- Chroma
- PostgreSQL with pgvector

## Use Cases

- Migrating data to vector databases
- Building RAG (Retrieval-Augmented Generation) applications
- Creating semantic search systems
- Data pipeline automation
- Batch embedding generation

## Pricing

Free and open-source under MIT license.