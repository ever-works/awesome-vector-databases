# OpenSearch Vector Search

OpenSearch Vector Search is the vector similarity and AI search capability within the OpenSearch engine. It provides a complete vector database solution that lets you store and search vector embeddings alongside traditional indexed data to power semantic search, RAG, recommendations, and other AI applications.

---

## Key Facts

- **Product type:** Vector search / vector database capability within OpenSearch
- **Category:** Multi-model & hybrid databases
- **Vendor / Project:** OpenSearch
- **Docs:** https://docs.opensearch.org/latest/vector-search/

---

## Features

### Core Vector Database Capabilities
- Store and search **vector embeddings** together with existing OpenSearch documents.
- Support for **vector indices** using k-NN / ANN style search.
- **Raw vector similarity search** over embedding fields.
- Integration with OpenSearch’s existing indexing, mappings, and query DSL.

### AI & Semantic Search
- **Semantic search** using dense vector embeddings.
- **Retrieval-Augmented Generation (RAG)** support by using vector search to retrieve context for LLMs.
- **Conversational search** scenarios using embeddings and OpenSearch queries.
- **Recommendation systems** and similar AI-powered applications built on top of embeddings.

### Hybrid & Multimodal Search
- **Hybrid search** combining vector similarity with traditional keyword / sparse search.
- **Multimodal search** support (e.g., combining different data modalities via embeddings).
- **Neural sparse search** capabilities for improved lexical relevance using neural models.

### Embedding & Model Integration
- Use **user-provided embeddings** (generated externally and indexed into OpenSearch).
- Optionally use **embeddings generated automatically** by OpenSearch’s ML Commons plugin.
- **Model registration & deployment**:
  - Register ML models (e.g., Hugging Face sentence-transformers models) via the ML Commons APIs.
  - Asynchronous model registration with task IDs and status tracking via the **Get ML Task API** (`/_plugins/_ml/tasks/`).
- **On-cluster model inference** on OpenSearch data nodes (configurable via cluster settings).  
  - Example: enabling `plugins.ml_commons.only_run_on_ml_node = false` for running models on data nodes in non-production environments.

### Ingest Pipelines & Automatic Embedding Generation
- **Ingest pipelines** for automatic embedding generation during indexing.
- `text_embedding` ingest processor to:
  - Call a registered ML model by `model_id`.
  - Map input text fields to output vector fields via `field_map` (e.g., `question_text` → `question_vector`).
- Ability to **test pipelines and models** using prediction endpoints (e.g., `/_plugins/_ml/_predict/text_embedding/`).
- Support for returning embedding vectors and specifying `target_response` fields (e.g., `sentence_embedding`).

### Indexing & Search Configuration
- Creation of **vector indices** with k-NN enabled via settings like `"index.knn": true`.
- Ability to associate a **default ingest pipeline** with an index (e.g., `"default_pipeline": "nlp-index-pipeline"`) so that embeddings are generated automatically on document ingestion.
- Use of OpenSearch mappings to define vector fields and other document fields.

### Tooling & Ecosystem
- Works within the broader **OpenSearch platform**, including:
  - OpenSearch as the core search & analytics engine.
  - OpenSearch Dashboards for visualization and exploration (implied from images / platform context).
- Integration with **ML Commons** plugin APIs for model lifecycle and inference.

---

## Typical Use Cases

- Building **semantic search** over text corpora.
- Implementing **RAG pipelines** where OpenSearch retrieves relevant context for LLMs.
- **Conversational search** and chat-style interfaces over enterprise or product data.
- **Product and content recommendations** using similarity search.
- **Hybrid search** experiences combining keyword relevance with vector semantics.

---

## Pricing

- No pricing information is provided in the referenced documentation. OpenSearch is an open-source project; deployment costs will depend on the chosen hosting / infrastructure.
