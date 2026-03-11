## Overview

Ollama provides local embedding generation capabilities, allowing you to run powerful embedding models completely offline on your computer. It's the recommended choice for building RAG applications locally with privacy.

## Supported Embedding Models

- **nomic-embed-text**: Large context length encoder surpassing OpenAI ada-002
- **nomic-embed-text-v2-moe**: Multilingual MoE text embedding model
- **mxbai-embed-large**: High-performance embedding model
- **all-minilm**: Efficient sentence transformer model

## Why Use Ollama for Embeddings

- **Completely Free**: No subscription fees or hidden costs
- **Offline Capable**: No internet connection required
- **Privacy**: Data never leaves your machine
- **Efficient**: Specialized models with smaller dimensions (1024 vs 4096 for LLMs)
- **Simple API**: Easy integration with localhost endpoint

## Usage

Default API endpoint at `http://localhost:11434/api/embeddings` with simple curl interface for generating embeddings.

## Integration

If you want to generate embeddings locally, Ollama with nomic-embed-text is the recommended approach. Widely supported across ChromaDB, LangChain, LlamaIndex, Haystack, and other RAG frameworks.

## Use Cases

- Local RAG applications
- Privacy-sensitive document processing
- Offline AI applications
- Development and testing without API costs
- Air-gapped environments

## Pricing

Completely free and open-source. No usage limits or API fees.