# Awesome-Moviate

**Category:** Open-source  
**Slug:** awesome-moviate  
**Brand:** weaviate  
**Source:** https://github.com/weaviate-tutorials/awesome-moviate

## Overview
Awesome-Moviate is an open-source demo of a movie search and recommendation engine. It showcases hybrid retrieval for media content by combining:
- BM25 keyword search
- Semantic vector search
- Hybrid search

It uses Weaviate as the underlying vector database.

## Features
- **Movie search demo UI** for exploring movie data and recommendations.
- **Hybrid retrieval pipeline** that blends:
  - BM25 keyword-based search
  - Vector-based semantic search
  - Combined hybrid search scoring.
- **Weaviate integration** as the vector database backend.
- **Data loading utilities** (e.g., `add_data.py`) to ingest movie datasets into Weaviate.
- **Predefined query logic** (e.g., `queries.js`) demonstrating different search modes.
- **Web application backend and routing** (e.g., `index.js`) for serving the search experience.
- **Frontend views** (in the `views` directory) for displaying search results and movie details.
- **Containerized setup with Docker** via `docker-compose.yml` to run Weaviate and the app locally.
- **Python and Node.js environment definitions** via `requirements.txt` and `package.json` for reproducible setup.
- **Example media asset** (`awesome-moviate-demo.gif`) demonstrating the application behavior.

## Tech Stack
- Weaviate (vector database)
- BM25 keyword search
- Semantic vector search
- Node.js (server, queries, app logic)
- Python (data ingestion scripts)
- Docker & Docker Compose

## Pricing
- Not applicable — Awesome-Moviate is an open-source demo project.