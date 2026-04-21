## Overview

Benchmarks compare relative performance rather than absolute numbers, run on identical affordable Azure machines (8 vCPU, 32GB RAM server), Dockerized with 25GB memory limit. Inspired by ann-benchmarks, tests multiple datasets with varying dimensions and distance metrics.

## Tested Scenarios

- **Upload & Search (Single Node)**: Indexing time, RPS, latency, p95 latency at different precision thresholds.
- **Filtered Search**: RPS and accuracy with payload filters (keywords, geo-spatial), highlighting issues like post/pre-filtering and HNSW disconnection.

## Datasets

| Dataset | # Vectors | Dimensions | Distance |
|---------|-----------|------------|----------|
| dbpedia-openai-1M-angular | 1M | 1536 | cosine |
| deep-image-96-angular | 10M | 96 | cosine |
| gist-960-euclidean | 1M | 960 | euclidean |
| glove-100-angular | 1.2M | 100 | cosine |

## Key Findings (Jan/June 2024)

- Qdrant: Highest RPS, lowest latencies across scenarios; 4x RPS gains on some datasets.
- Elasticsearch: Improved speed but 10x slower indexing for 96-dim 10M+ vectors.
- Milvus: Fastest indexing, good precision, but lags in high-dim RPS/latency.
- Redis: Good RPS/low precision, latency scales poorly with threads.
- Weaviate: Least improvement.

## Filtered Search Insights

Qdrant avoids speed/accuracy pitfalls via advanced query planning. Others show downturns or collapses.

## Reproduction

Fully open-sourced; see GitHub repository for setup.