---
title: WEAVESS
slug: weavess
category: benchmarks-evaluation
brand: lsyhprum
source_url: https://github.com/Lsyhprum/WEAVESS
featured: false
images:
  - https://opengraph.githubassets.com/1/Lsyhprum/WEAVESS
tags:
  - ann
  - benchmark
  - similarity-search
---

## Description

WEAVESS is an open-source benchmarking and evaluation framework for graph-based approximate nearest neighbor (ANN) search methods. It provides the code, datasets, optimal parameters, and experimental setup used in the paper *“A Comprehensive Survey and Experimental Comparison of Graph-based Approximate Nearest Neighbor Search”*. The framework is aimed at researchers and practitioners who need fair, reproducible comparisons of vector indexing algorithms for large-scale vector similarity search, vector databases, and AI search applications.

## Features

- **Comprehensive experimental framework**
  - Implements the full experimental pipeline used in the referenced survey paper.
  - Provides code, datasets, and detailed experimental configurations.
  - Ensures fair comparison by reimplementing all evaluated algorithms under a unified design pattern, programming language (with a noted exception for the IEH hash table), and common experimental setup.

- **Implemented / evaluated algorithms**
  - Supports benchmarking of thirteen representative graph-based ANNS algorithms:
    - **KGraph**
    - **FANNG**
    - **NSG (Navigating Spreading-out Graph)**
    - **NSSG**
    - **DPG**
    - **Vamana**
    - **EFANNA**
    - **IEH**
    - **NSW (Navigable Small World)**
    - **HNSW (Hierarchical NSW)**
    - **NGT-panng**
    - **NGT-onng**
    - **SPTAG-KDT**
    - **SPTAG-BKT**
    - **HCNNG**
    - **KDRG**
  - Includes links or references to original papers and, where available, original code repositories for each algorithm.

- **Standardized implementation details**
  - Algorithms reimplemented in a consistent way to reduce implementation bias in comparisons.
  - Uses the same set of implementation “tricks” and optimizations across methods where applicable.

- **Real-world datasets**
  - Includes eight real-world ANN datasets commonly used in prior work.
  - Each dataset is pre-split into:
    - **Base data** (indexing corpus)
    - **Query data** (evaluation queries)
  - Provides **ground truth neighbor data** for evaluation, in the form of top-20 or top-100 nearest neighbors.

- **Synthetic datasets for scalability studies**
  - Provides twelve synthetic datasets to analyze:
    - Scalability of each algorithm with respect to dataset size.
    - Performance under varying data distributions and characteristics.

- **Evaluation focus**
  - Designed for large-scale vector similarity search and ANN benchmarking.
  - Suitable for evaluating indexing methods used in vector databases and AI search systems.

## Use Cases

- Research on graph-based ANN algorithms and their comparative performance.
- Reproducing or extending the experiments from the WEAVESS survey paper.
- Benchmarking new ANN algorithms against a standardized suite of baselines and datasets.
- Evaluating vector indexing strategies for production vector databases or search applications.

## Pricing

- **Open-source**: No pricing information is provided; the project is available as open-source software via GitHub.