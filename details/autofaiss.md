## Overview

Autofaiss is a Python library developed by Criteo that automatically creates FAISS KNN indices with optimal similarity search parameters. It wraps the FAISS library and automatically tunes the best KNN index to maximize recall given RAM and query speed constraints.

## Key Features

- **Automatic Index Building**: Creates optimal indices based on memory and speed constraints
- **Hyperparameter Tuning**: Automatically sets hyperparameters to optimize the trade-off between recall and search time
- **Distributed Processing**: Supports building indices in parallel using PySpark
- **Index Scoring**: Provides metrics like recall and query speed evaluation
- **Performance**: Can automatically build large-scale indices (200 million vectors, 1TB) in 3 hours using low memory (15 GB) with millisecond latency (10ms)

## Problem Solved

FAISS offers hundreds of algorithm combinations with up to 6 hyperparameters per index type. Autofaiss eliminates the need to manually select and tune these parameters by automatically finding the optimal configuration for your specific requirements.

## Installation

Available via pip:
```
pip install autofaiss
```

## Use Cases

- Large-scale similarity search optimization
- Automatic index tuning for production deployments
- Distributed vector index creation
- Memory-constrained vector search applications