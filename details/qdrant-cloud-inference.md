# Qdrant Cloud Inference

**Category:** Cloud Services  
**Brand:** Qdrant  
**Website:** https://qdrant.tech/cloud-inference/  
**Images:**  
- https://qdrant.tech/images/cloud-inference/cloud-inference-hero.png

## Overview
Qdrant Cloud Inference is a managed inference capability integrated directly into Qdrant Cloud clusters. It allows you to generate and store text and image embeddings within the same environment where you perform vector search, removing the need for separate model servers or external embedding pipelines. It supports dense, sparse, and image models to enable semantic, keyword, hybrid, and multimodal search via a single API.

## Features

### Integrated in-cluster inference
- Generate embeddings inside the Qdrant Cloud cluster network.  
- No separate model server is required.  
- Eliminates the need for external embedding or ETL pipelines.  
- Embeddings are generated and stored directly where vector search is executed.

### Single API for search and embeddings
- Work with embedding generation and vector search from the same API surface.  
- Simplifies building and maintaining vector search pipelines.

### In-region, low-latency operation
- Embeddings are generated and search is executed in-region on:  
  - AWS  
  - Azure  
  - Google Cloud Platform (GCP, US regions)  
- Reduces latency by avoiding external network hops.  
- Avoids additional data egress and transfer overhead.  
- Suitable for real-time applications that are sensitive to delays.

### Support for multiple model types
- **Dense models** for semantic similarity search (e.g., `all-MiniLM-L6-v2`).  
- **Sparse models** for keyword and lexical recall (e.g., `splade-pp-en-v1`, `bm25`).  
- **Image and CLIP-style models** for image and text embeddings.  
- Enables building:
  - Semantic search
  - Keyword search  
  - Hybrid search (dense + sparse)  
  - Multimodal search (text + image).

### Hybrid and multimodal search capabilities
- Combine dense and sparse embeddings for improved relevance (hybrid search).  
- Use text and image embeddings together for multimodal search use cases.  
- All handled within Qdrant Cloud’s managed environment.

## Pricing
- Up to **5 million free tokens per model**, renewed monthly.  
- Additional pricing details are not specified in the provided content; refer to the official pricing page or documentation for full cost information.
