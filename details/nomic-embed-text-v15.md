## Overview

Nomic-embed-text-v1.5 is now multimodal, with nomic-embed-vision-v1.5 aligned to its embedding space, making text embeddings compatible with vision inputs.

## Key Features

- A large context length text encoder that surpasses OpenAI text-embedding-ada-002 and text-embedding-3-small performance on short and long context tasks
- Outperforms OpenAI's text-embedding-3-small on short context (MTEB 62.39 vs 62.26) and long context (LoCo 85.53 vs 82.40) benchmarks
- Utilizes Matryoshka Representation Learning, giving developers flexibility to trade off embedding size for negligible performance reduction
- Supports binary embeddings and Matryoshka embeddings for fine-tuned control over performance/disk space tradeoffs

## Technical Specifications

- Model checkpoint: v1.5
- Parameters: 137M
- Model size: 523 MB (float)
- Embedding dimensionality: Adjustable from 64 to 768 dimensions

## Usage

The text prompt must include a task instruction prefix - for RAG applications, documents are embedded as 'search_document: <text>' and queries as 'search_query: <text>'

## Availability

The model is available on multiple platforms including Hugging Face, Ollama, AWS Marketplace, and Qualcomm AI Hub.

## Pricing

Open-source and free to use.