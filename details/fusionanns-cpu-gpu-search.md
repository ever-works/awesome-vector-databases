## Overview

FusionANNS is a high-throughput, low-latency, cost-efficient, and high-accuracy ANNS system designed for billion-scale datasets. The system uniquely combines CPU and GPU resources along with SSD storage to achieve exceptional performance with minimal hardware requirements.

## Key Innovation: CPU/GPU Collaboration

The core innovation lies in CPU/GPU collaborative filtering and re-ranking mechanisms, which significantly reduce I/O operations across CPUs, GPU, and SSDs to break through the I/O performance bottleneck that typically limits billion-scale vector search.

## Three Novel Design Components

### 1. Multi-Tiered Indexing

FusionANNS employs a carefully designed three-tier architecture:
- **SSDs**: Store raw vectors
- **GPU HBM**: Hold compressed vectors using Product Quantization (PQ)
- **Host Memory**: Maintain only vector-IDs and navigation graph

This design avoids expensive data swapping between CPUs and GPU while maximizing the utility of each storage tier.

### 2. Heuristic Re-Ranking

Eliminate unnecessary I/Os and computations while guaranteeing high accuracy through intelligent query processing strategies.

### 3. Redundant-Aware I/O Deduplication

Further improves I/O efficiency by identifying and eliminating redundant data transfers during query processing.

## Performance Metrics

**Throughput**:
- Up to 13.1× higher QPS compared to SPANN
- 2-4.9× higher QPS compared to RUMMY
- Over 12,000 QPS for billion-vector datasets

**Latency**: As low as 15 milliseconds for billion-scale queries

**Cost Efficiency**:
- 8.8× better cost efficiency vs. SPANN
- 6.8× better cost efficiency vs. RUMMY
- Requires only one entry-level GPU

## Hardware Requirements

Unlike systems requiring expensive high-end GPUs or multiple GPUs, FusionANNS achieves exceptional performance with:
- One entry-level GPU
- Standard CPUs
- SSD storage

This makes billion-scale vector search accessible to organizations with moderate hardware budgets.

## Use Cases

- Large-scale semantic search
- Real-time recommendation systems
- High-throughput RAG applications
- Production deployments requiring cost-effective billion-scale search

## Research Origin

Developed by researchers from Huazhong University of Science and Technology and Huawei Technologies Co., Ltd., published September 2024 (arXiv:2409.16576).