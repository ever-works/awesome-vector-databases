## Overview

Embedding models transform raw data (text, images, audio) into dense numerical vectors that capture semantic meaning, enabling AI applications to understand and compare content.

## How They Work

1. **Input**: Raw data (text, image, etc.)
2. **Encode**: Neural network processes input
3. **Output**: Fixed-size vector (e.g., 768 dimensions)
4. **Property**: Similar inputs → similar vectors

## Types

### Text Embeddings
- Sentence-BERT
- BGE models
- OpenAI text-embedding-*
- Cohere Embed

### Multimodal
- CLIP (text + image)
- Gemini Embedding 2
- UForm

### Specialized
- Code embeddings
- Audio embeddings
- Graph embeddings

## Key Characteristics

### Dimensionality
- Small: 384-512 (fast, less info)
- Medium: 768-1024 (balanced)
- Large: 1536-4096 (rich, slower)

### Context Window
- Max input length
- Typically 512-8192 tokens
- Affects chunk size decisions

## Choosing Models

### Considerations
- **Task**: Search, classification, clustering
- **Language**: Monolingual vs multilingual
- **Domain**: General vs specialized
- **Performance**: Speed vs quality
- **Cost**: Self-hosted vs API

### Evaluation
- MTEB Leaderboard
- Task-specific benchmarks
- Domain testing

## Popular Models (2026)

- NV-Embed (NVIDIA)
- BGE-M3 (BAAI)
- Gemini Embedding 2
- text-embedding-3-* (OpenAI)
- Voyage embeddings
- Jina Embeddings v4/v5

## Pricing

- **Open Source**: Free (hosting costs)
- **APIs**: Usage-based pricing
- **Self-hosted**: Compute infrastructure