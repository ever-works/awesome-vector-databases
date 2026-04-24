# Lantern

Lantern is a PostgreSQL extension for multimodal vector search supporting text, image, and video vectors.

## Multimodal Vector Support

Handles embeddings from models like CLIP for text-to-image/video similarity, enabling cross-modal queries.

## Key Features

- Multi-modal indexing with tiered HNSW
- Fusion search: hybrid vector + BM25 text
- GPU/SIMD acceleration for sub-ms latency
- Disk persistence for billion-scale datasets
- Serverless indexing offload
- SQL-based embedding/LLM integration

## Use Cases

- Computer vision + text search (e.g., 'red car in city')
- Multimedia recommendations
- Real-time AI apps with persistent data

## Comparisons

**Vs text-only pgvector**: Extends pgvector-like functionality with native multimodal indexing, fusion, and GPU/disk optimizations for diverse media beyond text embeddings.

## Pricing

- Free tier: $0/month (multi-tenant)
- Self-hosted open-source
- Managed service available.