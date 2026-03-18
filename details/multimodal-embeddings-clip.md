## Overview

Multimodal embeddings map different data types (text, images, audio, video) into a shared vector space where semantic similarity is preserved across modalities.

## Key Models

**CLIP (Contrastive Language-Image Pre-training)**:
- OpenAI's foundational multimodal model
- Text and image embeddings in same space
- Zero-shot image classification
- Widely adopted baseline

**SigLIP**:
- Google's improved CLIP variant
- Better performance, especially zero-shot
- More efficient training

**Voyage Multimodal 3.5**:
- Text, images, screenshots, PDFs, and video
- Single transformer encoder for all modalities
- 4.56% better than Cohere Embed v4

**Jina CLIP**:
- Specialized for different use cases
- Good multilingual support

## Capabilities

**Cross-Modal Search**:
- Text → Image: "Find photos of sunset"
- Image → Text: Find descriptions of an image
- Image → Image: Visual similarity search

**Zero-Shot Classification**:
- Classify images without training
- Use text prompts as labels

**Visual Question Answering**:
- Answer questions about images
- Grounded in visual content

## Use Cases

- E-commerce visual search
- Content moderation (image + text)
- Digital asset management
- Video search and indexing
- Medical imaging with reports
- Scientific figure retrieval
- Social media analysis

## Implementation

```python
from sentence_transformers import SentenceTransformer

model = SentenceTransformer('clip-ViT-B-32')

# Embed images and text together
image_emb = model.encode(Image.open('photo.jpg'))
text_emb = model.encode("a photo of a sunset")

# Compute similarity
similarity = cosine_similarity(image_emb, text_emb)
```

## Vector Database Support

- Weaviate (native multi2vec-clip)
- Qdrant
- Milvus
- Pinecone
- Elasticsearch

## Best Practices

1. Use same model for all modalities
2. Normalize embeddings
3. Consider model size vs accuracy
4. Test on your specific use case
5. Combine with metadata filtering

## Recent Developments (2026)

- Voyage multimodal 3.5 adds video support
- Models handle interleaved text + images
- Better table and figure understanding
- Improved multilingual capabilities