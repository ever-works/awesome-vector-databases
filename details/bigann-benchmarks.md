## Overview

BigANN is the premier benchmark and competition for evaluating approximate nearest neighbor (ANN) search algorithms at billion-scale. Hosted at NeurIPS conferences, it provides standardized datasets and evaluation metrics for comparing vector search performance.

## Competition Tracks

- **Track T1**: Measures recall at 10,000 queries/second on 32 vCPUs
- **Track T2**: Measures recall at 1,500 queries/second
- **Track T3**: Measures recall at 2,000 queries/second

## Datasets

Includes billion-point datasets:
- BIGANN: SIFT descriptors from large image datasets
- Deep1B: Deep learning-based image descriptors
- Text datasets with various dimensionalities

## Evaluation Metrics

- **Recall**: Accuracy of approximate results vs exact results
- **Queries Per Second (QPS)**: Throughput performance
- **Index Build Time**: Time to construct the search index
- **Memory Usage**: RAM requirements for index and queries

## Notable Competitions

- NeurIPS 2021: First major billion-scale competition
- NeurIPS 2023: Expanded tracks and datasets

## Winners

Major technology companies and research labs have participated, including Intel, Microsoft (SPTAG), and others, advancing the state of the art in vector search.

## Use Cases

- Comparing vector search algorithms
- Benchmarking new ANN methods
- Academic research
- Industry validation of production systems

## Access

Datasets and evaluation code are publicly available for research purposes.