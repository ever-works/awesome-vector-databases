# Vertex AI Search ranking API

**Website:** https://cloud.google.com/generative-ai-app-builder/docs/ranking  
**Provider:** Google Cloud  
**Category:** Curated Resource Lists / AI & Machine Learning  
**Type:** API for document reranking

---

## Overview
Vertex AI Search ranking API is a Google Cloud service that reranks a list of documents (records) based on how well they answer a given query. It uses pretrained language models to go beyond basic semantic similarity and assign precise relevance scores, making it well-suited for improving search and Retrieval-Augmented Generation (RAG) pipelines.

The API is stateless: you don’t need to index documents beforehand. You supply a query and a set of records, and it returns the same records in a new order with relevance scores.

---

## Use Cases
- **Improve search result quality** after retrieving an initial candidate set from Vector Search or another search system.
- **RAG grounding:** find the most relevant pieces of content to pass to an LLM as grounding context.
- **Improve existing search experiences** by reranking results for better relevance to user intent.
- **Identify relevant sections within documents**, especially for long or chunked content.
- **Chunked-document workflows**, e.g.:
  - Split documents into chunks with Document AI Layout Parser.
  - Create embeddings for each chunk.
  - Load embeddings into Vector Search or another search solution.
  - Query and retrieve the most relevant chunks.
  - Rerank those chunks with the ranking API.

---

## Features

### Core Ranking
- **Query-based reranking**: Takes a natural-language query plus a list of records and returns the records ordered by relevance.
- **Precise relevance scoring**: Provides scores that indicate how well each record answers the query, beyond simple embedding similarity.
- **Complements vector search**: Intended to be used after an initial retrieval step from Vector Search or any other search backend.

### Stateless Operation
- **No indexing required**: The API does not maintain state or indexes. You send documents with each request.
- **Flexible integration**: Can be applied to results from different search systems or databases without changing underlying infrastructure.

### Input Data Model
- **Query input**: A text query string, e.g. `"Why is the sky blue?"`.
- **Records array**:
  - Each record can include:
    - `id` (unique identifier)
    - `title` (optional but recommended)
    - `content` (optional but recommended)
  - You must provide at least one of `title` or `content` per record.
- **Record limits**:
  - Up to **200 records per request**.
  - **Token limits per record** depend on model version:
    - Versions up to **`003`**: up to **512 tokens** per record.
    - Version **`004`**: up to **1024 tokens** per record.
  - If combined `title + content` exceeds the model’s token limit, the extra content is **truncated**.

### Output Control
- **Configurable number of results**: Optionally specify the maximum number of records to return. By default, all records are returned, reranked.

### Model Versions
- **Multiple model versions supported**, including at least:
  - `003`
  - `004`
- **Different token capacities**: newer versions (e.g., `004`) support longer records.

---

## Typical Workflow Integration

1. **Prepare documents**
   - Optionally split large documents into smaller chunks (for example, using Document AI Layout Parser).
2. **Initial retrieval**
   - Use an embeddings API to embed the chunks.
   - Load embeddings into Vertex AI Vector Search or another search solution.
   - Run a query to retrieve an initial set of candidate chunks or documents.
3. **Rerank with ranking API**
   - Send the query and the retrieved records to the ranking API.
   - Use the returned order and scores to select the most relevant content for search display or for RAG grounding.

---

## Pricing
The provided content does not include pricing details or plan information for the Vertex AI Search ranking API. Refer to Google Cloud’s official pricing pages for up-to-date pricing information.