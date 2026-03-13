## Overview

VDBBench is an open-source vector database benchmarking tool designed for comparing and evaluating vector databases. It's designed for users who require high-performance data storage and retrieval systems.

## Database Support

Supports testing of:
- Milvus
- Zilliz Cloud
- Elasticsearch
- Qdrant Cloud
- Weaviate Cloud
- PgVector

## Key Features

### Real-World Testing

VDBBench is the only benchmark tool that tests vector databases across the complete spectrum of production-critical scenarios:
- Static collection tests
- Filtering scenarios
- Streaming cases

### Comparison Capabilities

Offers the ability to select and compare results from multiple tests simultaneously, making it easy to understand relative performance across different vector databases.

## Modern Datasets

VDBBench uses vectors generated from state-of-the-art embedding models that power today's AI applications, moving beyond legacy datasets like SIFT and GloVe.

## Benchmark Metrics

VDBBench measures:
- p99 serial search latency
- Maximum concurrent QPS at 90% data capacity
- Performance while insertion workload remains active

## Availability

- **GitHub**: https://github.com/zilliztech/VectorDBBench
- **PyPI**: Can be installed via pip as vectordb-bench
- **Leaderboard**: Public results viewable at the VDBBench Leaderboard

## Use Cases

- Evaluating vector databases for production deployments
- Comparing performance across different solutions
- Validating POC requirements match production capabilities
- Performance regression testing

## Pricing

Free and open-source.