# Vertex AI Feature Store

**Website:** https://cloud.google.com/vertex-ai/docs/featurestore  
**Category:** Curated Resource Lists / ML Feature Management  
**Vendor / Brand:** Google Cloud  
**Type:** Managed feature store (cloud service)

---

## Overview

Vertex AI Feature Store is a managed feature management service on Google Cloud that lets you maintain and serve machine learning features from a centralized repository. It uses BigQuery as the primary offline data source and provides online serving capabilities for low-latency inference, including vector/embedding support for similarity search. It is commonly used in production recommendation, ranking, and search systems, often in combination with vector search.

The Vertex AI feature management offering currently includes:
- **Vertex AI Feature Store** (new, BigQuery-based, metadata layer with online serving)
- **Vertex AI Feature Store (Legacy)** (original, with separate online and offline stores inside Vertex AI)

---

## Features

### Core Feature Management
- Centralized storage and management of ML features for multiple models and use cases.
- Support for creating, maintaining, sharing, and serving features from a single repository.
- Facilitates feature reuse across training and prediction workflows to shorten ML lifecycle.
- Feature registry to register, share, and reuse features across teams and projects.

### Data Storage & Architecture (New Vertex AI Feature Store)
- **BigQuery as offline feature store**: store and maintain offline feature data directly in BigQuery.
- No need to copy or import offline data into a separate Vertex AI store; Feature Store acts as a metadata and serving layer on top of BigQuery.
- Leverages BigQuery’s data management capabilities (scalability, governance, and analytics) for offline features.

### Online Serving
- **Low-latency online serving** for real-time prediction workflows.
- **Serving backends:**
  - Bigtable-based online serving for low-latency feature retrieval.
  - Optimized online serving for ultra-low latency access.
- Ability to serve feature values in production for recommendation, ranking, and search systems.

### Embeddings & Vector Capabilities
- Support for storing embeddings as features.
- Vector similarity search (nearest-neighbor search) over stored embeddings using Optimized online serving.
- Designed to integrate with vector indexes and vector search to enrich or filter results.

### Metadata & Governance
- Integration with **Dataplex Universal Catalog** for feature metadata tracking.
- Centralized catalog of feature definitions and metadata to aid discoverability and governance.

### Legacy Vertex AI Feature Store (Feature Management v1)
- Separate **online store** and **offline store** provisioned within Vertex AI.
- **Offline store capabilities:**
  - Batch or streaming import of feature data from Cloud Storage, BigQuery, and similar sources.
  - Storage of historical feature data for training and batch serving.
- **Online store capabilities:**
  - Serves most recent feature values for online predictions.
- Full feature management workflow: ingest → store (offline + online) → serve (batch + online).
- Migration path and tooling to move from Legacy Feature Store to the new Vertex AI Feature Store.

---

## Integrations
- **BigQuery** – primary offline feature data source; used for storing and maintaining feature tables.
- **Bigtable** – backend for low-latency online serving (new Feature Store).
- **Dataplex Universal Catalog** – feature metadata catalog and governance.
- Works alongside **vector search** / vector indexes for production recommendation and search systems.

---

## Use Cases
- Real-time recommendations (e.g., products, content, ads) requiring low- or ultra-low-latency feature access.
- Search and ranking systems enriched with ML features and embeddings.
- Centralized feature registry for multiple ML models and teams.
- Training and retraining ML models using consistent, reusable feature definitions.

---

## Pricing

The provided content does not include pricing or plan details for Vertex AI Feature Store. For up-to-date pricing information, see the official Google Cloud Vertex AI pricing pages.