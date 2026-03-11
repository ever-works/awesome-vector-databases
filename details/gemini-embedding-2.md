## Overview

Gemini Embedding 2 is Google's first natively multimodal embedding model, released March 10, 2026. It maps text, images, videos, audio and documents into a unified embedding space, capturing semantic intent across more than 100 languages.

## Key Features

### Multimodal Support

- **Text**: Up to 8,192 input tokens
- **Images**: Up to 6 images per request (PNG or JPEG)
- **Audio**: Maximum 80 seconds per request (MP3 or WAV)
- **Video**: Maximum 128 seconds per request (MP4 or MOV)
- **Documents**: PDF files up to 6 pages directly

### Flexible Dimensions

Supports multiple output dimensions:
- 3,072 dimensions (default)
- 1,536 dimensions
- 768 dimensions

Uses Matryoshka Representation Learning for dimension truncation without significant accuracy loss.

### Language Support

Captures semantic relationships across over 100 languages, making it suitable for global applications.

## Performance

Gemini Embedding 2 establishes new performance standards:
- Outperforms leading models in text, image, and video tasks
- Strong speech capabilities for audio processing
- Superior multimodal depth in cross-modal retrieval

## Use Cases

- **Semantic Search**: Multi-language and multimodal search applications
- **RAG Systems**: Retrieval-Augmented Generation with diverse data types
- **Sentiment Analysis**: Text and audio sentiment understanding
- **Data Clustering**: Grouping similar content across modalities
- **Recommendation Systems**: Cross-modal content recommendations
- **Content Moderation**: Multi-format content classification
- **Video Understanding**: Temporal and visual content analysis

## Integration

Available through:
- Google Gemini API
- Vertex AI
- LangChain
- LlamaIndex
- Haystack
- Weaviate
- Qdrant
- ChromaDB
- Vertex AI Vector Search

## Technical Specifications

- **Model Type**: Multimodal embedding transformer
- **Context Window**: 8,192 tokens for text
- **Embedding Dimensions**: 768 / 1,536 / 3,072
- **Languages**: 100+
- **Modalities**: Text, Image, Video, Audio, Documents

## Pricing

Pricing varies based on:
- Number of API calls
- Input modality and size
- Output dimension selection

Details available on Google Cloud pricing page.