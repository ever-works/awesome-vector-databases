# Azure Cosmos DB Vector Indexing

**Category:** Multi-model & Hybrid Databases  
**Brand:** Microsoft Azure  
**Slug:** `azure-cosmos-db-vector-indexing`

## Overview
Azure Cosmos DB Vector Indexing adds native vector storage and search to Azure Cosmos DB for NoSQL. It lets you store multi-modal, high-dimensional vector embeddings directly in documents alongside other JSON data and perform efficient vector similarity search at scale using built-in vector index types.

## Features

### Native vector storage
- Store vector embeddings as properties within the same documents that hold your application data.
- Supports multi-modal, high-dimensional vectors (e.g., text, images, audio embeddings).
- Co-locates vectors and associated data in a single logical unit for simpler data management and query patterns.

### Vector index types
- **Flat index (exact kNN / brute-force):**
  - Performs exact k-nearest neighbors search.
  - Provides 100% recall.
  - Suited for smaller or more focused vector search scenarios.
  - Works well when combined with query filters and partition keys.

- **Quantized flat index:**
  - Compresses vectors using DiskANN-based quantization methods.
  - Enables more efficient brute-force kNN search over large datasets by reducing memory and storage footprint.

- **DiskANN index:**
  - Uses Microsoft Research’s DiskANN algorithms for approximate nearest neighbor (ANN) search.
  - Designed for efficient, high-accuracy multi-modal vector search at large scale.
  - Optimized for low latency and cost-efficient operation on large vector collections.

### Integrated querying
- Vector search is exposed through the `VectorDistance` function in Azure Cosmos DB queries (NoSQL API).
- Vector similarity search can be combined with other query filters using `WHERE` clauses.
- Works with existing Cosmos DB indexing and partitioning, enabling:
  - Hybrid queries that filter on document fields and then apply vector similarity.
  - Scenario-specific filtering (e.g., by user, region, time range) plus vector search.

### Performance and scale characteristics
- Designed for low-latency and high-throughput vector similarity search directly within Cosmos DB collections.
- Supports both exact brute-force search and approximate nearest neighbor search, so you can trade off accuracy vs performance and cost.
- Architecture supports scalable handling of large, high-dimensional vector datasets used in AI applications.

### AI and multi-modal application support
- Suitable for storing and querying embeddings produced by external ML or LLM services (e.g., Azure OpenAI Embeddings, Hugging Face on Azure, or other embedding models).
- Enables scenarios such as semantic search, recommendation systems, similarity search for text and images, and anomaly detection.
- Simplifies AI application architectures by removing the need for a separate vector database—vectors live in the same system as transactional data.

### Future / preview capabilities (as described)
- Azure Cosmos DB is developing enhanced vector search features for ultra-high throughput workloads:
  - Designed for very large vector datasets.
  - Targets millions of queries per second with predictable low latency.
  - Focus on cost-efficient, high-scale vector search.
- Early access is available through a separate private preview sign-up.

## Images
- Vector search architecture: `https://learn.microsoft.com/azure/cosmos-db/media/cosmos-db-vector-search/vector-search-architecture.png`
- Vector index policy configuration: `https://learn.microsoft.com/azure/cosmos-db/media/cosmos-db-vector-search/vector-index-policy.png`

## Tags
- `vector-search`
- `diskann`
- `cloud-native`

## Pricing
The provided content does not specify pricing or plan details for Azure Cosmos DB Vector Indexing. Refer to Azure Cosmos DB pricing documentation for current costs related to storage, throughput, and any vector indexing or query charges.