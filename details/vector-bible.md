## Overview

Vector Bible is a performance comparison framework for vector databases, using pre-generated embeddings from a multilingual Bible dataset (bible.helloao.org/bible.db, 8.4GB SQLite exported to Postgres). Tests focus on API times (not embedding generation), with Docker limits (6 CPU, 12.8GB RAM). Multilingual embeddings generated via sentence-transformers/paraphrase-multilingual-mpnet-base-v2 (768 dims, HNSW index, Cosine similarity).

## Key Metrics

| Nr | Engine | Ports | UI | Stability | Precision | Insert Speed (1k batch) | Search (21k) | Search (1.4M) | HDD | RAM | Ease |
|----|--------|-------|----|-----------|-----------|-------------------------|--------------|---------------|-----|-----|------|
| 2 | Qdrant 1.11.0 | 6334 6333 | 🟢 | 🟢 | 🟢 8/10 | 🟢 0.129s => 0.4s | 🟢 0.008s | 🟢 0.031s | 🟢 4.8GB | 🟢 4.73GB | ★★★★☆ |
| 5 | Weaviate 1.24.22 | 8080 50051 | 🔴 | 🟢 | 🟡 4/10 | 🟡 0.411s => 2s | 🟢 0.006s | 🟢 0.010s | 🟢 8.41GB | 🟡 8.16GB | ★★★☆☆ |
| 6 | Elastic 8.15 | 5601 9200 | 🟢 | 🟢 | 🟢 10/10 | 🔴 2.917s | 🟢 0.008s | 🟡 0.20s => 🟢0.011s | 🔴 23.46GB | 🟢 5.1GB | ★★★☆☆ |
| 7 | ChromaDB 0.5.5 | 8000 | 🔴 | 🟢 | 🟡 4/10 | 🔴 1.21s => 4s | 🟢 0.018s | 🟡 1.26s => 🟢0.022s | 🟡 12.37GB | 🟢 4.86GB | ★★★★☆ |
| 3 | Milvus 2.4.8 | 9091 19530 8000 | 🟢 | 🟡 | 🔴 0/10 | 🟢 0.118s => 0.4s | 🔴 0.234s | 🟡 0.358s | 🔴 15GB | 🟢 4.59GB | ★★★☆☆ |
| 4 | Redis stack 7.4 | 6379 8001 | 🟢 | 🟡 | 🟡 3/10 | 🔴 0.8s => 7s | 🟢 0.002s | 🟢 0.003s (knn) | 🟢 6GB | 🔴 10.5GB | ★★★☆☆ |
| 1 | Postgres 16.4 + pgvector 0.7.4 | 5432 | 🟡 | 🟢 | 🟡 5/10 | -- | 🟡 0.069s | 🔴 6.39s (L1) etc. | 🟡 11.2GB | 63MB | ★★☆☆☆ |
| 8 | Marqo 2.11 | 8882 | 🔴 | - | N/A | 🔴 4.14s | 🟡 0.19s => 0.030s | N/A | 🟢 5GB | ★★☆☆☆ |

## Usage

Data prep: Import SQLite to Postgres, generate embeddings, create HNSW indexes. Run docker-compose for each DB, execute Python scripts (e.g., 1-pgvector.py, 2-qdrant.py). Visualize with cosmograph.info using exported CSV nodes/edges (similarity >0.95).

## Notes

Excludes cloud-only (Pinecone, etc.). Links to other benchmarks: vectorview.ai, vendor-specific. Subjective ease based on docs/API/UI setup.