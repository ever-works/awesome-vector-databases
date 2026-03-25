## Overview

VectorDBBench Leaderboard is the public-facing benchmark results platform that provides standardized performance comparisons of vector databases across diverse testing scenarios that closely mimic real-world production environments.

## Testing Scenarios

The leaderboard includes results for:

- **Insertion Performance**: Measuring write throughput and latency
- **Search Performance**: Query latency and throughput at various scales
- **Filtered Search**: Performance with metadata filtering
- **Recall Accuracy**: Measuring search quality vs speed trade-offs
- **Cost Efficiency**: Comparing total cost of ownership

## Datasets Used

- SIFT (128-dimensional vectors)
- GIST (960-dimensional vectors)
- Cohere embeddings (768-dimensional)
- OpenAI generated datasets
- Real production scenario data

## Supported Databases

Currently benchmarks 15 cases across 6+ clients including:

- Milvus
- Zilliz Cloud
- Elasticsearch
- Qdrant Cloud
- Weaviate Cloud
- PgVector
- And more...

## Key Features

- **Reproducible Results**: Open-source benchmarking tool allows reproduction
- **Production-Like Workloads**: Realistic testing scenarios
- **Multi-Dimensional Comparison**: Performance, cost, accuracy metrics
- **Regular Updates**: Leaderboard updated with new databases and versions
- **Public Data**: All results publicly accessible

## How to Use

1. Visit the leaderboard at zilliz.com/vdbbench-leaderboard
2. Filter by dataset, operation type, or specific databases
3. Compare metrics across different configurations
4. Download raw data for custom analysis
5. Run benchmarks yourself using the open-source tool

## Tool Installation

Install the benchmarking tool:
```bash
pip install vectordb-bench
init_bench
```

## Use Cases

- Evaluating vector databases for new projects
- Performance tuning and optimization guidance
- Cost analysis for production deployments
- Understanding trade-offs between accuracy and performance
- Vendor selection and evaluation

## Sponsorship

Sponsored by Zilliz but includes results from multiple vector database vendors and open-source solutions.