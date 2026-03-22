## Overview

embed-multilingual-v3.0 is a high-performance embedding model from Cohere's Embed V3 model family, specifically tailored for multilingual text representation with support for 100+ languages.

## Key Features

- **Dimensionality**: 1024 dimensions
- **Languages**: 100+ languages supported
- **Training Data**: Nearly 1B English and 0.5B non-English training pairs
- **Cross-lingual**: Search within and across languages

## Capabilities

### Within-Language Search
Search with a French query on French documents

### Cross-Language Search
Search with a Chinese query on Finnish documents

## Use Cases

- **Multilingual Semantic Search**: Find relevant content across languages
- **RAG (Retrieval Augmented Generation)**: Context retrieval for LLMs
- **Text Classification**: Categorize text in multiple languages
- **Document Clustering**: Group similar documents regardless of language

## Input Types

Requires specifying input type for optimal performance:
- `input_type="search_document"`: For embedding passages/documents
- `input_type="search_query"`: For embedding search queries

## Availability (2026)

Accessible through multiple platforms:
- Cohere API
- AWS SageMaker
- Azure AI
- Oracle Cloud Infrastructure
- Private deployments with CUDA driver 12.2+ and NVIDIA driver 535+

## Integration

- Compatible with major vector databases
- Supported by LangChain and LlamaIndex
- RESTful API access