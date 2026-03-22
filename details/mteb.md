## Overview

MTEB (Massive Text Embedding Benchmark) is the most comprehensive benchmark for evaluating text embedding models. It covers 8 different embedding tasks across 58 datasets in 112 languages, providing a standardized way to compare embedding quality.

## Evaluated Tasks

MTEB evaluates models across 8 core tasks:

1. **Classification**: Text categorization and labeling
2. **Clustering**: Grouping similar texts
3. **Pair Classification**: Determining if text pairs are related
4. **Reranking**: Ordering candidates by relevance
5. **Retrieval**: Finding relevant documents for queries
6. **Semantic Textual Similarity (STS)**: Measuring text similarity
7. **Summarization**: Evaluating summary quality
8. **BitextMining**: Cross-lingual sentence alignment

## Key Features

- **Comprehensive Coverage**: 58 datasets across diverse domains
- **Multilingual**: Supports 112 languages
- **Standardized Evaluation**: Consistent metrics across all models
- **Public Leaderboard**: Compare models transparently
- **Easy Integration**: Simple Python API

## Top Models (as of 2026)

Historically strong performers include:
- Voyage embeddings (voyage-3, voyage-4)
- Jina embeddings (jina-embeddings-v3, v4)
- Cohere embed-v3 and v4
- BGE-M3 (multilingual)
- E5 models (Microsoft)
- GTE models (Alibaba)

## Metrics

Different metrics for each task:
- **Classification/Clustering**: Accuracy, F1
- **Retrieval**: NDCG@10, MAP, Recall
- **STS**: Spearman correlation
- **Reranking**: MAP, MRR

## Why MTEB Matters

- **Industry Standard**: De facto benchmark for embedding models
- **Comprehensive**: Tests multiple capabilities, not just retrieval
- **Practical**: Tasks reflect real-world applications
- **Transparent**: Public leaderboard with reproducible results
- **Updated**: Regular addition of new models and datasets

## Using MTEB

```python
from mteb import MTEB

# Evaluate a model
evaluation = MTEB(tasks=["Banking77Classification"])
results = evaluation.run(model)
```

## Limitations

- Bias toward certain types of tasks
- Some datasets may be in training data
- Static evaluation (no dynamic updates)
- Resource intensive to run full benchmark

## Leaderboard

Official leaderboard maintained on Hugging Face:
https://huggingface.co/spaces/mteb/leaderboard

## Resources

- **GitHub**: github.com/embeddings-benchmark/mteb
- **Paper**: Available on arXiv
- **Documentation**: Comprehensive guides

## Use Cases

- **Model Selection**: Choose best embedding for your use case
- **Model Development**: Benchmark new architectures
- **Research**: Compare against state-of-the-art
- **Production**: Validate model performance

## Pricing

Free and open-source benchmark.