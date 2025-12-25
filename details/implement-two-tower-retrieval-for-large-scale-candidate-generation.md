# Implement two-tower retrieval for large-scale candidate generation

- **Type**: Reference architecture / technical guide
- **Provider**: Google Cloud
- **Category**: Curated resource list / Architecture pattern
- **Topics**: RAG, semantic search, large-scale recommendation, two-tower retrieval
- **URL**: https://cloud.google.com/architecture/implement-two-tower-retrieval-large-scale-candidate-generation

## Overview

This reference architecture describes how to design and implement an end-to-end two-tower retrieval system for large-scale candidate generation using Google Cloud, Vertex AI, and vector similarity search. It focuses on learning and serving semantic similarity between entities (for example, web queries and candidate items) in large-scale recommendation and personalization systems with low-latency serving requirements.

Primary audience: data scientists and machine learning engineers building large-scale recommenders and retrieval systems.

## Key Concepts

- **Two-tower (dual encoder) model**: Two separate neural networks (towers) independently encode:
  - **Query tower**: user/query features
  - **Candidate tower**: item/candidate features
  These towers produce embeddings that can be compared via vector similarity.

- **Candidate generation stage**:
  - First stage in a two- or multi-stage recommender architecture.
  - Filters millions of items down to hundreds of relevant candidates.
  - Designed for high throughput and low latency.

- **Ranking stage**:
  - Second stage that re-ranks the candidate subset.
  - Produces the final set of recommended items.

- **Semantic similarity learning**:
  - Learns similarity between `<query, candidate>` pairs
  - Uses vector similarity search to efficiently retrieve nearest neighbors in embedding space.

## Architecture

The architecture demonstrates how to:

- **Train a two-tower model** on Google Cloud.
- **Deploy each tower separately** for different serving and deployment tasks.
- **Use vector similarity search** for large-scale retrieval from a large corpus of candidate items.

High-level components (as shown in the diagrams and description):

- A training pipeline that learns a dual-encoder (two-tower) model.
- A **query tower** service that encodes queries or user context at request time.
- A **candidate tower** service that encodes items/candidates, typically offline or periodically.
- A vector index (vector similarity search) storing candidate embeddings for large-scale approximate nearest neighbor (ANN) search.
- A candidate generation service that retrieves top candidates from the vector index.
- A downstream ranking component that further filters and sorts the retrieved candidates.

## Products Used

The reference architecture uses the following Google Cloud products (as stated or implied):

- **Vertex AI**
  - Model training for the two-tower architecture
  - Model deployment for serving each tower independently
- **Vector similarity search** (Vertex AI Vector Search or equivalent Google Cloud vector indexing) for large-scale nearest neighbor retrieval in embedding space

## Use Cases

- Large-scale recommendation systems that must:
  - Serve recommendations with **low latency**
  - Handle **millions of candidate items**
  - Support **two-stage or multi-stage** architectures (candidate generation + ranking)
- Personalization scenarios where you need to learn semantic similarity between:
  - Search queries and documents/items
  - Users and items
  - Any `<query, candidate>` entity pairs

## Features

- **End-to-end reference design** for a two-tower retrieval system on Google Cloud.
- **Separation of concerns**:
  - Independent training and deployment of query and candidate towers.
- **Scalable candidate generation**:
  - Efficiently filters a very large candidate pool to a manageable set of hundreds of items.
- **Low-latency retrieval**:
  - Uses vector similarity search to support fast, high-throughput queries.
- **Semantic retrieval**:
  - Embedding-based matching of queries and candidates via learned semantic similarity.
- **Integration with multi-stage recommenders**:
  - Designed to feed downstream ranking models.
- **Guidance on modeling and data preparation (via linked resources)**:
  - Refers to “Scaling deep retrieval with TensorFlow Recommenders and Vector Search” for details on model design, problem framing, and data preparation.

## Pricing

This item is a free **reference architecture / documentation page**. There is no direct pricing for the document itself. Any costs arise from using underlying Google Cloud services (for example, Vertex AI and vector search), which are priced separately in Google Cloud’s standard pricing documentation.