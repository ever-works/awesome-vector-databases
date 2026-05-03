## Overview

VAST AI OS is a GPU-accelerated data platform that includes a native vector database as a core capability of the broader VAST DataBase. It is designed for demanding enterprise AI workloads such as multi-agent systems, video-reasoning, and high-volume RAG, which require real-time processing, high throughput, complex queries, and extremely low latency.

The system combines the VAST AI OS with NVIDIA data-processing libraries (cuVS, cuDF) and onboard NVIDIA RTX PRO 6000 Blackwell Server Edition GPUs on the VAST CNode-X server, leveraging the NVIDIA AI Data Platform reference design.

## Architecture

- Vector embeddings are stored alongside structured data and metadata in the same tables
- Natively integrated with unstructured data in the VAST DataStore
- Enables hybrid queries across modalities without orchestration layers or external indexes
- Eliminates the need for separate CPU resources dedicated to indexing

## Performance Capabilities

- Sustained ingestion rate of 1 million vectors/second
- Benchmarked at very high throughput, performance, and recall across 50 billion vectors
- Indexing lifecycle (read 20% sample → K-means clustering → vector assignment → read/write) is 4.5x faster on GPU vs CPU-only approach
- K-means clustering and assignment phases especially benefit from GPU processing, producing more balanced clusters with fewer cycles
- A 10-hour CPU indexing process can execute in ~2.5 hours on GPU

## Use Cases

- Real-time RAG pipelines with near real-time ingestion and indexing
- Recommendation systems requiring high speed and accuracy
- Video-reasoning over public safety streams
- Finance, cybersecurity, genomics/life sciences, retail, and chemistry applications
- Multi-agent concurrent SQL query execution

## GPU Acceleration

- Uses NVIDIA cuVS as the GPU backend for vector search
- Uses NVIDIA cuDF for GPU-accelerated data processing (Spark, pandas, Polars)
- Eliminates the need for expensive memory-based indexing and third-party vector databases
- Reduces indexing time by 4.5x compared to CPU-only FAISS approach

## Sirius SQL Engine

VAST's native SQL engine leverages the Sirius library to build GPU-accelerated operators for fast SQL-query execution. The Sirius database is built on NVIDIA cuDF, is natively compatible with DuckDB, and has shown up to 20x speedup over CPU-based DuckDB on NVIDIA RTX PRO 6000 GPUs.

## Pricing

Commercial product from VAST Data. Contact VAST Data for pricing details.