## Overview

ColQwen2 is a late-interaction visual retrieval model that extends the ColPali architecture using the Qwen2-VL backbone. It treats documents as images to capture not only text but also layout, tables, charts, and other visual elements.

## Key Advantages Over ColPali

- **Higher Accuracy**: +5 nDCG@5 points on the ViDoRe dataset
- **Permissive Licensing**: Apache 2.0 and MIT licenses for both base model and adapter
- **Fewer Patch Embeddings**: Uses 768 patches vs ColPali's 1024, reducing compute and storage
- **Dynamic Resolution**: Accepts images in their native aspect ratios without resizing

## Technical Architecture

- **Base Model**: Qwen2-VL-2B-Instruct
- **Patch Embeddings**: 768 image patches per page
- **Training**: Effective batch size of 32
- **Multi-Vector Approach**: Generates multiple vectors per document for fine-grained matching

## How It Works

Instead of relying on OCR and text extraction, ColQwen2:
1. Treats each document page as an image
2. Uses vision-language model to understand visual and textual elements together
3. Generates multi-vector embeddings that capture layout and content
4. Performs late interaction similarity matching at query time

## Use Cases

- PDF document retrieval without preprocessing
- Visual question answering over documents
- Form understanding and table extraction
- Scientific paper search with figures and equations
- Legal document retrieval with complex layouts
- Multimodal RAG applications

## Integration

- Vespa for production deployments
- Weaviate for vector storage
- Compatible with late-interaction retrieval frameworks
- Available through Hugging Face Transformers

## Performance Benefits

- No chunking or preprocessing required
- Preserves document layout information
- Better understanding of visual elements
- More accurate than text-only retrieval on complex documents

## Pricing

Open-source under Apache 2.0 and MIT licenses. Free for both academic and commercial use.