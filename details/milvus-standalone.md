---
title: Milvus Standalone
slug: milvus-standalone
brand: Milvus
brand_logo: https://milvus.io/img/milvus-logo.svg
source_url: https://milvus.io/
category: vector-database-engines
tags:
  - vector-database
  - single-node
  - similarity-search
  - production
  - genai
featured: false
images:
  - https://milvus.io/img/milvus-architecture.png
---

## Overview

Milvus Standalone is the single-machine deployment option of the open-source Milvus vector database. It provides a complete, production-ready vector search engine suitable for workloads with up to millions of vectors, making it a fit for both testing and smaller-scale production GenAI applications.

## Features

- **Single-node deployment**
  - Runs as a standalone instance on a single machine.
  - Suitable for environments where distributed infrastructure is not required.

- **Complete vector database**
  - Full Milvus feature set for vector search (same core database capabilities as other Milvus deployments).
  - Supports building and querying vector indexes for similarity search.

- **Production or testing use**
  - Can be used for local development and testing.
  - Robust enough for production scenarios where a single-node deployment is sufficient.

- **Scale target**
  - Designed for datasets with **up to millions of vectors** while maintaining high-performance search.

- **GenAI-focused**
  - Built for GenAI and LLM-based applications that rely on vector similarity search.

- **High-performance vector search engine**
  - Optimized for high-speed similarity search over vector embeddings.

- **Container-based setup**
  - Typical installation and running via Docker (as indicated by the “prerequisite-docker” documentation path).

- **Part of a broader deployment family**
  - Shares APIs and behavior with Milvus Lite and Milvus Distributed, easing migration to larger deployments if needed.

## Use Cases

- Local or on-premise single-machine vector database for GenAI applications.
- Small to medium production deployments where data volume is in the millions of vectors.
- Staging or testing environment mirroring a larger distributed Milvus setup.

## Deployment & Integration

- **Installation**
  - Deployed using Docker-based installation flows (see Milvus Standalone install docs).

- **Client usage example (Milvus family)**
  - Python client workflow shared across Milvus deployments:

    ```python
    from pymilvus import MilvusClient

    client = MilvusClient("milvus_demo.db")
    client.create_collection(
      collection_name="demo_collection",
      dimension=5
    )
    ```

  - The same client patterns apply when targeting a Milvus Standalone instance instead of a local file.

## Pricing

- Milvus Standalone is part of the **open-source Milvus** project.
- No specific commercial pricing or plans are described on the referenced content.
- Infrastructure and operational costs depend on the user’s own single-machine environment.
