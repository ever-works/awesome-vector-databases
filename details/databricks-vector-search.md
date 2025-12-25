# Databricks Vector Search

**Category:** Curated Resource Lists  
**Brand:** Databricks  
**Website:** https://www.databricks.com/product/machine-learning/vector-search

![Databricks Vector Search UI](https://www.databricks.com/wp-content/uploads/2023/11/product-vector-search-ui.png)

## Overview
Databricks Vector Search is a managed vector search capability integrated with the Databricks Lakehouse. It allows you to create and maintain vector search indexes over Delta tables, enabling similarity search for AI and Retrieval-Augmented Generation (RAG) applications. It supports different modes for handling embeddings and integrates with Unity Catalog and Delta Lake.

## Features

- **Managed vector search service**
  - Fully managed vector indexing and search on Databricks Lakehouse
  - Built to support AI, LLM, and RAG-style applications

- **Indexing over Delta tables**
  - Create vector search indexes directly on Delta tables
  - Indexes stay in sync with underlying Delta data depending on index type

- **Multiple embedding management modes**
  - **Delta Sync Index with managed embeddings**  
    - Databricks computes and manages embeddings for your data
    - Automatic embedding generation and index updates as source Delta tables change
  - **Delta Sync Index with self-managed embeddings**  
    - Use your own precomputed embeddings stored in Delta tables
    - Index stays synchronized with your precomputed embedding columns
  - **Direct Vector Access Index**  
    - Clients manage vector inserts, updates, and deletes directly via REST APIs
    - Does not require syncing from Delta; suitable for low-latency or external vector updates

- **Similarity search**
  - Vector-based similarity queries over documents, rows, or entities
  - Designed for use in retrieval and grounding for LLM applications

- **Metadata filtering**
  - Combine vector similarity search with structured metadata filters
  - Filter results by attributes (e.g., type, source, time) alongside semantic similarity

- **Integration with Databricks ecosystem**
  - **Unity Catalog integration** for governance and access control on indexed data
  - **Delta Lake integration** to leverage transactionally consistent tables as sources
  - Works within the Databricks Machine Learning / Lakehouse environment

- **API access and operations**
  - REST APIs for Direct Vector Access Index operations (e.g., add, update, delete vectors)
  - Programmatic management of indexes and queries from applications

- **Architecture options**
  - Supports architectures where embeddings are:
    - Computed inside Databricks (managed)
    - Computed externally and written to Delta (self-managed)
    - Sent directly via API without relying on Delta sync (direct access)

## Pricing

Pricing details are not provided in the supplied content. Refer to the official product page for current pricing and plan information:  
https://www.databricks.com/product/machine-learning/vector-search
