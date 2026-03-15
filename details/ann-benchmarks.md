## Overview

ANN-Benchmarks is a comprehensive benchmarking project for approximate nearest neighbor algorithms. It provides standardized datasets, evaluation metrics, and comparison results for various ANN libraries in Python.

## Key Features

- **Standardized Datasets**: Common benchmark datasets across all algorithms
- **Fair Comparison**: Same hardware, same evaluation methodology
- **Multiple Metrics**: Recall, queries per second, index build time
- **Open Source**: Transparent methodology and reproducible results
- **Regular Updates**: Continuous updates with new algorithms

## Benchmarked Algorithms

### Graph-Based
- HNSW (multiple implementations)
- NSG
- NGT
- DiskANN

### Tree-Based
- Annoy (Spotify)
- MRPT
- RPForest

### Hash-Based
- FALCONN
- LSH variants

### Quantization-Based
- FAISS (all variants)
- ScaNN
- PQ-based methods

### Composite
- SPTAG
- N2

## Standard Datasets

### SIFT1M
- 1M 128-dimensional SIFT features
- Most common benchmark
- Moderate dimensionality

### GIST1M
- 1M 960-dimensional GIST features
- High dimensionality test

### GloVe
- Word embeddings
- Various sizes: 25/50/100/200 dimensions
- NLP applications

### Deep1B
- 1 billion deep learning features
- Scalability test
- 96 dimensions

## Evaluation Metrics

### Recall@K
- Percentage of true k-nearest neighbors found
- Most important quality metric
- Typical target: 95%+ recall

### Queries Per Second (QPS)
- Throughput metric
- Higher is better
- Hardware-dependent

### Build Time
- Index construction time
- One-time cost
- Important for dynamic datasets

### Memory Usage
- Index size in RAM
- Critical for large-scale deployments

## Recall-QPS Trade-off

Key insight from benchmarks:
- No single winner across all scenarios
- Trade-off between speed and accuracy
- Different algorithms excel at different points

### High Recall (>99%)
- HNSW often wins
- Graph methods dominate
- Higher memory usage

### Balanced (90-95% recall)
- FAISS-IVF competitive
- Good speed-accuracy balance
- Lower memory

### Speed-Optimized (<90% recall)
- Quantized methods shine
- LSH variants
- Lowest latency

## Typical Results

### Winner by Category

**Best Accuracy**: HNSW
**Best Speed (given accuracy)**: ScaNN, HNSW
**Best Memory Efficiency**: FAISS-IVF-PQ
**Best Build Time**: LSH methods
**Best Overall**: HNSW (for most use cases)

## How to Use

### Running Benchmarks
```bash
# Clone repository
git clone https://github.com/erikbern/ann-benchmarks

# Install dependencies
pip install -r requirements.txt

# Run benchmark
python run.py --algorithm hnsw

# Generate plots
python plot.py --dataset sift-128-euclidean
```

### Adding Custom Algorithm
1. Implement standard interface
2. Add algorithm configuration
3. Run benchmarks
4. Compare results

## Insights from Benchmarks

### HNSW Dominance
- Consistently high performance
- Good across different datasets
- Gold standard for many applications

### FAISS Versatility
- Multiple index types
- Good for different requirements
- Excellent with GPU

### ScaNN for Inner Product
- Best for dot product similarity
- Anisotropic quantization advantage
- Good speed-accuracy trade-off

### Annoy Simplicity
- Easy to use
- Good for moderate scale
- Memory-mapped for large datasets

## Limitations

- Python-only benchmarks
- Limited to single-machine
- Specific datasets may not match your domain
- Hardware-dependent results
- Doesn't test all features (filtering, updates)

## Complementary Benchmarks

### Big-ANN Benchmarks
- Billion-scale datasets
- Out-of-memory scenarios
- Disk-based methods

### VectorDBBench
- Full database systems (not just algorithms)
- Real-world scenarios
- Filtering and updates

## Best Practices

1. **Start Here**: Use ANN-Benchmarks for initial algorithm selection
2. **Test Your Data**: Results vary by dataset characteristics
3. **Consider All Metrics**: Not just recall-QPS
4. **Production Testing**: Benchmark on your actual data and queries
5. **Update Regularly**: Algorithms improve over time

## Reproduction

All results are reproducible:
- Docker containers for consistency
- Fixed random seeds
- Documented hardware specs
- Open-source code

## Contributing

- Add new algorithms
- Submit new datasets
- Improve methodology
- Report issues

GitHub: github.com/erikbern/ann-benchmarks

## Pricing

Free and open-source (MIT license).