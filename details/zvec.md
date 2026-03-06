## Overview

Zvec is a lightweight, lightning-fast, in-process vector database released by Alibaba Tongyi Lab in February 2026. It runs as a library inside your application with no external service or daemon required, making it the SQLite of vector databases.

## Key Features

- **In-Process Architecture**: Runs wherever your code runs — notebooks, servers, CLI tools, or edge devices
- **Dense + Sparse Vectors**: Work with both dense and sparse embeddings, with native support for multi-vector queries
- **Hybrid Search**: Combine semantic similarity with structured filters for precise results
- **Built on Proxima**: Powered by Alibaba's production-grade, battle-tested vector search engine
- **WAL Support**: Provides Write-Ahead Logging for data durability
- **RAG Ready**: Full CRUD operations, schema evolution, multi-vector retrieval, built-in reranking (weighted fusion and RRF)

## Performance

Zvec delivers >8,000 QPS on VectorDBBench with the Cohere 10M dataset, achieving more than 2× the performance of previous leaderboard leaders while reducing index build time.

## Platform Support

- Python 3.10 to 3.12
- Linux x86_64, Linux ARM64, macOS ARM64
- Install with: `pip install zvec`

## Use Cases

- Retrieval Augmented Generation (RAG)
- Semantic search on edge devices
- Agent workloads requiring local execution
- Mobile and constrained hardware deployments

## Pricing

Free and open-source under Apache 2.0 license. No licensing costs.