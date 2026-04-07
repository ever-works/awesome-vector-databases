## Overview

RuVector is a self-learning vector memory and agentic operating system built on PostgreSQL, with capabilities for storing embeddings, graph queries, and running local LLMs. It features SONA engine for real-time adaptation, GNN for improving search results, and supports deployment in servers, browsers, IoT via WASM.

## Core Features

- Store vectors with HNSW indexing and SIMD acceleration
- Query with Cypher graph queries including hyperedges
- Self-learning index via GNN layers that adapt from every query
- Hyperbolic HNSW for hierarchy-aware search
- Automatic compression with 2-32x memory reduction
- Metadata filtering and multi-tenant collections
- Snapshots for point-in-time backups

## Advanced Search & Retrieval

- Hybrid search with sparse + dense vectors and RRF fusion (20-49% better retrieval)
- Graph RAG with knowledge graph and community detection (30-60% improvement)
- DiskANN/Vamana for billion-scale SSD-backed ANN (<10ms latency)
- ColBERT multi-vector late interaction retrieval
- Matryoshka embeddings for adaptive-dimension search
- OPQ optimized product quantization
- LSM compaction for write-heavy workloads
- GraphMAE self-supervised learning
- TurboQuant 2-4 bit KV-cache quantization (6-8x memory savings)

## Continuous Training & Optimization

- Nightly LoRA fine-tuning from query learnings
- Automated release gates with 7 quality checks
- TurboQuant profiling per layer
- Training corpus from brain memories and examples

## Distributed Systems

- Raft consensus and multi-master replication
- Cluster management with consistent hashing
- Delta consensus with CRDTs
- Burst scaling and auto-sharding

## AI & Machine Learning

- Local LLM inference on Metal, CUDA, WebGPU
- RuvLTRA pre-trained models
- SONA self-optimizing neural architecture
- 50+ attention mechanisms including FlashAttention-3, graph, hyperbolic
- Semantic routing and sparse inference
- Domain expansion and transfer learning
- Advanced math solvers (PageRank, spectral clustering)

## Graph Transformers

- 8 modules: physics-informed, biological, self-organizing, manifold, temporal-causal, economic
- Proof-gated mutation and verified training

## Cognitive Containers (RVF)

- Single .rvf file boots as microservice with kernel (125ms)
- eBPF acceleration
- WASM runtime (5.5 KB)
- COW branching, witness chains, post-quantum crypto

## PostgreSQL Extension

- Drop-in pgvector replacement with 230+ SQL functions
- Sublinear solvers, math distances, topological analysis in SQL

## Specialized Processing

- Genomics (rvDNA): variant calling, HNSW k-mer search
- SciPix OCR, DAG workflows, quantum coherence

## Pricing

Free and open-source under the MIT license.