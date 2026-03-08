## Overview

Big-ANN Benchmarks is a community-driven competition and benchmark suite designed to evaluate approximate nearest neighbor search algorithms at billion-scale. It provides standardized datasets, metrics, and evaluation protocols.

## Key Datasets

### Billion-Scale Datasets
- **SIFT1B**: 1 billion 128-dimensional SIFT descriptors
- **Deep1B**: 1 billion 96-dimensional deep learning features
- Additional large-scale datasets for diverse evaluation scenarios

## Benchmark Tracks

### 2023 Competition Tracks
- **Out-of-distribution track**: Tests generalization to unseen data distributions
- **Streaming track**: Evaluates performance with continuous data ingestion
- Both tracks test algorithms at billion-scale

## ScaNN SOAR Performance

ScaNN with SOAR achieved:
- Best query speed / indexing speed trade-off among all libraries
- Smallest memory footprint
- Highest results in both out-of-distribution and streaming tracks of Big-ANN 2023

## Evaluation Metrics

- Recall at various k values
- Query latency
- Index building time
- Memory consumption
- Throughput (QPS)

## Importance

Big-ANN Benchmarks provides:
- Standardized comparison across algorithms
- Real-world scale testing
- Community consensus on performance
- Reproducible evaluation methodology

## Access

Datasets and evaluation tools available at https://big-ann-benchmarks.com/

## Community Impact

Serves as the definitive benchmark for:
- Vector database vendors
- Academic research
- Algorithm development
- Production system design decisions