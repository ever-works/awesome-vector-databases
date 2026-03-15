## Overview

Voyage AI provides state-of-the-art embedding models optimized for retrieval tasks. Their models consistently rank highly on MTEB benchmarks and offer both text-only and multimodal capabilities.

## Models

### voyage-4 (Latest, 2026)
- Latest generation model
- Enhanced retrieval performance
- Support for longer contexts
- Improved multilingual capabilities

### voyage-3-large
- High-quality text embeddings
- 1024 dimensions
- Strong MTEB performance
- Good for general-purpose retrieval

### voyage-multimodal-3
- Text and image embeddings
- Unified embedding space
- Cross-modal search

### voyage-multimodal-3.5 (2026)
- Enhanced multimodal capabilities
- Better image-text alignment
- Improved zero-shot performance

## Key Features

- **Retrieval-Optimized**: Trained specifically for search tasks
- **Domain Adaptation**: Fine-tune on your specific domain
- **Multilingual**: Support for 100+ languages
- **Long Context**: Handle up to 32K tokens
- **Batch Processing**: Efficient bulk embedding generation

## API Usage

```python
import voyageai

vo = voyageai.Client(api_key="...")

# Text embeddings
result = vo.embed(
    texts=["Document 1", "Document 2"],
    model="voyage-3-large"
)

embeddings = result.embeddings
```

## Use Cases

- Semantic search
- RAG applications
- Document clustering
- Question answering
- Recommendation systems

## Pricing

Usage-based pricing per 1M tokens, typically competitive with OpenAI and Cohere.