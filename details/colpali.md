## Overview

ColPali is a Vision Language Model trained to produce high-quality multi-vector embeddings from images of document pages for efficient document retrieval.

## Key Features

### Architecture

ColPali uses PaliGemma-3B to encode images by:
- Splitting images into patches fed to a vision transformer (SigLIP-So400m)
- Patch embeddings linearly projected as "soft" tokens to a language model (Gemma 2B)
- Creating contextualized patch embeddings projected to lower dimension (D=128)

### Main Advantage

ColPali removes the need for potentially complex and brittle layout recognition and OCR pipelines with a single model that can take into account both the textual and visual content (layout, charts, etc.) of a document.

### Retrieval Method

ColPali runs a ColBERT-style "late interaction" operation to efficiently match query tokens to document patches, computing a score by searching for the document patch with the most similar representation for each query term.

## Performance

Combined with a late interaction matching mechanism, ColPali largely outperforms modern document retrieval pipelines while being drastically simpler, faster and end-to-end trainable.

## Benchmark

The Visual Document Retrieval Benchmark (ViDoRe) was introduced to assess retrievers on their capacity to retrieve visually rich information in docs, with tasks spanning various topics, modalities (figures, tables, text), and languages.

## Use Cases

- Visual document search
- PDF retrieval without OCR
- Multimodal RAG systems
- Document understanding pipelines
- Enterprise document search

## Pricing

Free and open-source.