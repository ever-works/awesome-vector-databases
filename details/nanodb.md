## Overview

NanoDB is a GPU-optimized database for text/image vectors using CLIP embeddings, enabling realtime text-to-image search on edge devices.

## Multimodal Vector Support

Shared embedding space for text and images (float16 disk storage); supports PNG/JPG/TIFF/etc.

## Features

- Multi-modal indexing for text-to-image
- Fusion-style similarity in CLIP space
- CUDA acceleration on Jetson/NVIDIA
- Incremental scanning and autosave
- Gradio UI for search
- Duplicate detection/validation

## Use Cases

- CV + text search (e.g., on MS COCO dataset)
- Edge multimedia recommendations
- LLM RAG with images

## Comparisons

**Vs text-only pgvector**: NanoDB specializes in vision-language multimodal search with GPU realtime performance on edge, storing only embeddings without full images.

## Usage

Indexing:
```
python3 -m nanodb --scan /dataset --path /nanodb --autosave --validate
```

Search: `a girl riding a horse`

Server:
```
python3 -m nanodb --path /nanodb --server --port=7860
```

## Pricing

Free and open-source.