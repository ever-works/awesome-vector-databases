# Lantern

Lantern is an open-source PostgreSQL extension and toolkit that provides efficient vector search capabilities and enables developers to build production-ready AI applications directly within their PostgreSQL databases. It allows users to perform similarity searches, advanced text searches, and integrate AI workflows without requiring separate vector databases or search engines.

## Features

*   **Vector Search with pgvector:** Supports searching over sparse and dense vectors, including binary, scalar, and product compression. It scales seamlessly to millions of vectors with serverless indexing.
*   **Text Search with BM25:** Utilizes the BM25 ranking algorithm for more relevant text search results, surpassing the default full-text search capabilities in PostgreSQL.
*   **Hybrid Search:** Combines vector search and BM25 text search using RRF or other reranking algorithms for enhanced results.
*   **Serverless Indexing:** Offloads vector index creation to a separate machine from the main database, allowing effortless scaling without compromising database performance.
    *   Provides infinite scalability, adapting resource usage to needs.
    *   Enables building or updating indexes without slowing down the database.
    *   Offers seamless integration by simply adding `external=true` to vector index creation.
*   **Embedding Generation and LLM Integrations:** Simplifies AI workflows by allowing direct generation of embeddings and running LLMs within the database using simple SQL commands.
    *   Supports over 20 embedding models and LLMs, including OpenAI, Cohere, and Jina AI.
    *   Automatically generates new vector or LLM columns based on existing data.
*   **Easy to Use:** Integrates directly with SQL and popular ORMs, eliminating the need to learn new APIs or frameworks.
*   **Deployment Options:** Available as open-source for self-hosting or as a managed service (Lantern Cloud).

## Pricing

*   **Free tier:** $0.00/month. This is a multi-tenant setup that never pauses and includes vector search and indexing capabilities.
