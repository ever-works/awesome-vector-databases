# Vertex AI Embeddings

**URL:** https://cloud.google.com/vertex-ai/docs/generative-ai/embeddings  
**Category:** Curated Resource Lists  
**Provider / Brand:** Google Cloud  
**Type:** Managed embeddings service (API)

---

## Overview

Vertex AI Embeddings is a managed Google Cloud service that generates vector (numerical) representations of text and multimodal content (images and video). These embeddings capture semantic relationships between inputs and are typically used with vector databases or vector search services to power search, retrieval, recommendation, and other AI applications.

The service converts text, images, and videos into arrays of floating-point numbers (vectors), where distances between vectors correspond to similarity between the underlying objects.

---

## Features

### Core Capabilities
- **Text embeddings**
  - Converts text into dense vectors representing semantic meaning.
  - Supports use cases like semantic search, classification, clustering, outlier detection, and conversational interfaces.
- **Multimodal embeddings**
  - Generates embeddings for images, text, and video.
  - Enables cross-modal use cases such as text-to-image search or video similarity search.

### Text Embeddings Features & Use Cases
- **Semantic search**
  - Rank or retrieve text documents based on semantic similarity rather than exact keyword matching.
- **Classification**
  - Use embeddings as features to classify items whose text attributes are similar to labeled examples.
- **Clustering**
  - Group items with similar text attributes (for example, documents, product descriptions, or support tickets).
- **Outlier detection**
  - Identify items whose text attributes are least related to a given query or to a cluster of typical items.
- **Conversational interface support**
  - Cluster sentences or conversation turns in an embedding space so that similar queries map to similar responses.
- **Example application: recommendation chatbot**
  - Represent each item (e.g., book) as an embedding built from title, content, and metadata (such as genre).
  - Use similarity between book vectors to recommend similar items.
  - Combine with generative models to summarize and recommend content based on a user’s query.

### Multimodal Embeddings Features & Use Cases
- **Image + text scenarios**
  - **Image classification**: Use embeddings as input features to predict one or more labels for an image.
  - **Image search**: Search for relevant or similar images by comparing image embeddings or text-to-image similarity.
  - **Image-based recommendations**: Recommend products or ads based on visual similarity between item images.
- **Image + text + video scenarios**
  - **Video recommendations**: Generate product or advertisement recommendations based on video similarity.
  - **Video content search**: Search within video collections using semantic similarity.
  - **Text-to-video frame search (semantic search)**
    - Input: text query.
    - Output: ranked video frames that semantically match the query.
  - **Video-to-video similarity search**
    - Input: a video.
    - Output: similar videos or segments based on embedding similarity.

### Embedding Representation
- **Vector representation**
  - Converts inputs (text, image, video) into arrays of floating-point numbers.
  - Captures semantic meaning and relationships in a continuous vector space.
- **Vector dimensionality**
  - Each embedding has a fixed length (number of dimensions) representing different learned features.
  - Distances between vectors (for example, cosine or Euclidean) indicate similarity or dissimilarity.
- **Input-driven embedding space**
  - The choice of input features (title only vs. title + summary + metadata) changes the structure of the embedding space and which items end up close together.

### Integration Patterns
- **Works with vector databases / vector search**
  - Designed to populate and update vector indexes for similarity search.
  - Can be integrated into retrieval-augmented generation (RAG) and other search-heavy architectures.

---

## Pricing

The provided content does not contain any pricing or plan information. Refer to the official Vertex AI pricing page on Google Cloud for current details.