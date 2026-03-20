## Overview

Jina-CLIP v2 is a state-of-the-art multimodal embedding model that combines text and image understanding in a single unified model. It represents a significant improvement over v1 with enhanced multilingual capabilities and higher resolution image processing.

## Architecture

The model combines two specialized encoders:
- **Text Encoder**: Jina XLM-RoBERTa (561M parameters)
- **Vision Encoder**: EVA02-L14 (304M parameters)
- **Total Parameters**: 865M

## Key Features

- **Multilingual Support**: Supports 89 languages for text-image retrieval with up to 4% improvement over comparable models
- **High Resolution**: Processes 512x512 images, a significant upgrade from v1's 224x224 resolution
- **Matryoshka Representations**: Allows truncating output dimensions from 1024 to 64 while maintaining 99% performance
- **State-of-the-Art Performance**: Achieves 98.0% accuracy on Flickr30k image-to-text retrieval
- **Flexible Deployment**: Available via Jina Embeddings API, AWS, Azure, and GCP

## Performance

Even aggressive 75% dimensional reduction maintained over 99% performance across text, image, and cross-modal tasks. The model shows 3% performance improvement over v1 in both text-image and text-text retrieval tasks.

## Use Cases

- Cross-modal search (text-to-image, image-to-text)
- Multilingual image retrieval
- Visual question answering
- Content-based recommendation systems
- Multimodal RAG applications

## Pricing

Available through Jina Embeddings API with commercial licensing. Also available on cloud marketplaces (AWS, Azure, GCP) with usage-based pricing.