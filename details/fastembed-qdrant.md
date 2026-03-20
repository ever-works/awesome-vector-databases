## Overview

FastEmbed is Qdrant's lightweight Python library for generating embeddings efficiently without GPU requirements or heavy dependencies.

## Key Features

**Lightweight**: Few external dependencies, no PyTorch (uses ONNX Runtime)

**Fast**: Faster than PyTorch for inference

**Accurate**: Better than OpenAI Ada-002 with Flag Embedding

**Serverless-Friendly**: Small footprint ideal for AWS Lambda

## Embedding Types

- **TextEmbedding**: Standard text embeddings
- **LateInteractionTextEmbedding**: ColBERT-style embeddings
- **ImageEmbedding**: Image embeddings
- **LateInteractionMultimodalEmbedding**: Multimodal applications

## Installation

```bash
pip install fastembed
# With GPU support
pip install fastembed-gpu
```

## Use Cases

- Serverless embedding generation
- Edge deployments
- Resource-constrained environments
- High-throughput embedding pipelines
- Integration with Qdrant vector database

## Availability

Open-source on GitHub: qdrant/fastembed

Supports LangChain integration