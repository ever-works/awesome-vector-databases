# Oracle AI Vector Search

**Website:** <https://www.oracle.com/database/ai-vector-search/>

Oracle AI Vector Search is an integrated vector search capability within Oracle AI Database 26ai. It adds a native VECTOR data type and vector indexes so you can store and query vector embeddings alongside relational, text, JSON, spatial, and graph data. It supports high‑dimensional semantic similarity search for AI workloads such as RAG, chatbots, recommendation systems, anomaly detection, and multimedia search, directly on enterprise business data.

---

## Features

### Integrated vector search in Oracle AI Database 26ai
- Native VECTOR data type for storing vector embeddings in database tables.
- Works alongside existing data types (relational, text, JSON, spatial, graph) in a single converged database.
- Enables similarity search (by semantics/meaning) and traditional value-based search in the same queries.

### Unified hybrid vector search
- Combine vector similarity search with:
  - Relational data
  - Text search
  - JSON data
  - Knowledge graph data
  - Spatial/location data
- Retrieve and rank documents, images, videos, audio, and structured data by considering both semantic similarity and structured filters.
- Supports building applications that mix semantic search on unstructured data with relational search on business data for more relevant and secure results.

### Vector generation and ingestion
- Flexible ways to generate and load embeddings:
  - Use open-source embedding models via the ONNX framework.
  - Use database APIs to call external embedding model providers.
  - Import precomputed vectors directly into the database.
- Store embeddings and business data together for consistent governance and querying.

### Hybrid vector indexes and performance
- Vector indexes for approximate similarity search to accelerate semantic queries.
- In-memory neighbor graph index for maximum performance on similarity search workloads.
- Neighbor partition indexes for scalable, high-dimensional search over large datasets.

### End-to-end generative AI and RAG pipeline (in-database)
- Native or API-based capabilities within the database for:
  - Document loading
  - Data transformation and chunking
  - Embedding generation
  - Similarity/vector search
  - Retrieval-Augmented Generation (RAG) with large language models
- Designed to improve LLM accuracy and contextual relevance on private enterprise data while reducing hallucinations.

### AI application development
- Use preferred development tools, AI frameworks, models, and programming languages.
- Build AI applications (e.g., chatbots, recommendation systems, anomaly detection, multimedia search) directly against Oracle AI Database 26ai.

### Enterprise-grade characteristics (as described)
- Intended for mission-critical AI applications.
- Built on Oracle Database capabilities for scalability, performance, high availability, and security.
- Focus on keeping data in-place (“bring AI to your data”) instead of moving it into separate vector stores.

---

## Typical Use Cases

- Retrieval-augmented generation (RAG) over enterprise data for LLM-based applications.
- Natural language and semantic search over private business content.
- Multimedia search across images, video, and audio using embeddings.
- Recommendation and personalization systems based on vector similarity.
- Anomaly and pattern detection in high-dimensional data.

---

## Pricing

The provided content does not include any pricing or plan details for Oracle AI Vector Search. Refer to the official Oracle site or sales channels for current pricing information.