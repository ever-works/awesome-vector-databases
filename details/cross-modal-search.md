## Overview

Cross-modal search enables finding content in one modality using queries in another, such as searching images with text or finding videos with audio descriptions.

## Modality Pairs

### Text-to-Image
**Query**: "sunset over mountains"
**Results**: Matching images

### Image-to-Text
**Query**: [photo]
**Results**: Captions, descriptions, articles

### Text-to-Video
**Query**: "basketball dunk compilation"
**Results**: Relevant video clips

### Audio-to-Image
**Query**: [sound of ocean waves]
**Results**: Beach imagery

## Enabling Models

### CLIP (OpenAI)
- Text and images
- Shared 512-dim space
- Strong zero-shot capabilities

### ImageBind (Meta)
- 6 modalities: text, image, audio, video, depth, IMU
- Unified embedding space
- Novel applications

### Gemini Embedding 2
- Text, images, video, audio, documents
- 3072-dim space
- Production-ready

## Implementation

```python
import clip
import torch

# Load CLIP
model, preprocess = clip.load("ViT-B/32")

# Embed text query
text = clip.tokenize(["sunset over mountains"])
text_embedding = model.encode_text(text)

# Search image database
results = vectordb.search(
    collection="images",
    query_vector=text_embedding,
    limit=10
)
```

## Use Cases

- E-commerce: "find similar looking products"
- Media libraries: Search videos by description
- Accessibility: Find images matching text
- Content moderation: Flag inappropriate content
- Creative tools: Find visuals matching mood

## Challenges

- Modality gap (embeddings not perfectly aligned)
- Domain-specific fine-tuning often needed
- Computational cost
- Quality varies by model

## Pricing

Depends on embedding model (CLIP is free/open-source, Gemini has API costs).