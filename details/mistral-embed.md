## Overview

mistral-embed is Mistral AI's general-purpose embedding model that transforms text into 1024-dimensional vector representations, capturing semantic meaning for various NLP tasks.

## Technical Specifications

- **Dimensions**: 1024
- **Normalization**: Norm 1 vectors (cosine similarity, dot product, and Euclidean distance are equivalent)
- **Processing**: Batch processing support for improved efficiency
- **Input**: Any text length

## Companion Model: Codestral-Embed

Mistral also offers **codestral-embed** for code-specific use cases:
- **Dimensions**: Up to 3072 (configurable via output_dimension)
- **Purpose**: Code search, repository analysis, coding assistants
- **Use Cases**: Semantic code search, duplicate detection, code analytics

## Use Cases

- **Retrieval Systems**: Power RAG pipelines with semantic retrieval
- **Clustering**: Group similar documents or code snippets
- **Classification**: Categorize text at scale
- **Semantic Search**: Find conceptually similar content
- **Duplicate Detection**: Identify similar or duplicate content
- **Code Search**: Navigate codebases semantically

## Distance Metrics

Due to norm 1 normalization, all these metrics are equivalent:
- Cosine similarity
- Dot product
- Euclidean distance

## API Integration

Available through Mistral AI's Embeddings API with support for:
- Batch processing
- Multiple text inputs
- Configurable output dimensions (codestral-embed)

## Integration Support

- LangChain
- LlamaIndex
- Qdrant
- Elasticsearch
- Custom implementations