## Overview

UForm is a pocket-sized multimodal AI framework for content understanding and generation across multilingual texts, images, and video. Designed for efficiency, it performs up to 5x faster than OpenAI CLIP and LLaVA while maintaining high accuracy.

## Key Features

### Multimodal Capabilities

- **Text**: Multilingual text understanding and embedding
- **Images**: Visual content encoding and understanding
- **Video**: Temporal visual understanding (upcoming)
- **Joint Embeddings**: Shared embedding space for cross-modal retrieval

### Performance

- **5x Faster**: Than OpenAI CLIP and LLaVA
- **Quantization-Aware**: Down-casting from f32 to i8 without significant recall loss
- **Efficient**: Optimized for production deployments

### Multilingual Support

Great recall across 20+ languages thanks to balanced multilingual training datasets.

## Available Models (v3)

### Image-Text Models

#### English Variants

- **uform3-image-text-english-large**: 365M parameters (best accuracy)
- **uform3-image-text-english-base**: 143M parameters (balanced)
- **uform3-image-text-english-small**: 79M parameters (fastest)

#### Multilingual

- **uform3-image-text-multilingual-base**: 206M parameters
- Supports 20+ languages

### Generative Models

- **Image Captioning**: Generate descriptions from images
- **Visual Question Answering (VQA)**: Answer questions about images
- **Conversational**: Multi-turn dialogue about visual content

## How It Works

### Encoding Pipeline

1. **Separate Processing**: Images and text processed independently
2. **Feature Extraction**: Generate features from each modality
3. **Embedding Generation**: Create embeddings in shared space
4. **Similarity Computation**: Cosine similarity for cross-modal matching

### Multimodal Embeddings

Joint embeddings created from both text and image features can be used to:
- Better rerank nearest neighbors
- Cross-modal search (text-to-image, image-to-text)
- Multimodal similarity

## Use Cases

- **Visual Search**: Find images using text queries or vice versa
- **Content Moderation**: Understand and classify multimodal content
- **Image Captioning**: Automatic description generation
- **VQA Systems**: Question answering about images
- **Multilingual Applications**: Cross-language image search
- **Recommendation**: Multimodal content recommendations
- **Semantic Search**: Unified search across text and images

## Platform Support

### Deployment Options

- **Python**: pip install uform
- **Web (JavaScript/WASM)**: Browser-based inference
- **iOS**: Native mobile deployment
- **ONNX**: Cross-platform runtime
- **PyTorch**: Native PyTorch support

## Integration

### APIs

```python
# Encode images and text
image_embeddings = model.encode_image(images)
text_embeddings = model.encode_text(texts)

# Compute similarity
similarity = cosine_similarity(image_embeddings, text_embeddings)
```

### Available on

- PyPI (Python package)
- npm (JavaScript/TypeScript)
- HuggingFace Hub (model weights)
- Replicate (API service)

## Model Comparison

### vs OpenAI CLIP

- 5x faster inference
- Smaller model sizes
- Competitive accuracy
- Better multilingual support

### vs LLaVA

- 5x faster
- More compact models
- Optimized for production

## Technical Specifications

- **Embedding Space**: Shared multimodal space
- **Quantization**: f32, f16, i8 support
- **Input Resolution**: Configurable for images
- **Batch Processing**: Optimized batch inference
- **Languages**: 20+ supported

## Advanced Features

### Quantization-Aware Training

Models trained with quantization in mind:
- Minimal accuracy loss when quantized
- i8 (int8) embeddings with high recall
- Smaller memory footprint
- Faster inference

### Reranking Support

Joint multimodal embeddings for improved reranking:
- Combine text and image signals
- Better top-k selection
- Enhanced retrieval accuracy

## Pricing

Free and open-source. Available on:
- GitHub: unum-cloud/UForm
- HuggingFace Hub
- API services (Replicate) with usage-based pricing