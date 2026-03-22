## Overview

BEIR (Benchmarking IR) is a heterogeneous benchmark for information retrieval that evaluates models across 18 publicly available datasets spanning 9 different retrieval tasks. It's designed to test zero-shot performance of retrieval models.

## Key Characteristics

### Zero-Shot Evaluation
BEIR tests models in a zero-shot setting, meaning:
- No fine-tuning on target datasets
- Tests true generalization capability
- Reflects real-world deployment scenarios
- Measures robustness across domains

### Diverse Datasets

18 datasets covering:
- **Question Answering**: Natural Questions, HotpotQA
- **Fact Checking**: FEVER, Climate-FEVER
- **Citation Prediction**: SCIDOCS
- **Duplicate Question Detection**: Quora, CQADupStack
- **Argument Retrieval**: ArguAna, Touché-2020
- **News Retrieval**: TREC-NEWS
- **Bio-Medical**: NFCorpus, TREC-COVID
- **Entity Retrieval**: DBPedia
- **Tweet Retrieval**: Signal-1M

## Evaluation Metrics

Primary metrics:
- **NDCG@10**: Normalized Discounted Cumulative Gain
- **Recall@100**: Fraction of relevant documents in top 100
- **MAP**: Mean Average Precision
- **MRR**: Mean Reciprocal Rank

## Why BEIR Matters

- **Industry Standard**: Widely used for comparing retrieval models
- **Generalization Test**: Shows real-world performance
- **Domain Diversity**: Tests across different types of queries and documents
- **Research Baseline**: Standard benchmark for new retrieval methods

## Top Performing Models

Historically strong performers:
- Dense retrieval models (ANCE, ColBERT)
- Instruction-tuned embeddings (Instructor)
- Cross-encoders (for reranking)
- Hybrid approaches (combining dense + sparse)

## Limitations

- English-only datasets
- Relatively small dataset sizes for some tasks
- Static evaluation (doesn't capture temporal changes)
- Limited multimodal content

## Use Cases

- **Model Selection**: Choose embedding model for your application
- **Research**: Benchmark new retrieval architectures
- **Production Validation**: Estimate real-world performance
- **Model Development**: Identify weaknesses and improvement areas

## Integration

Easy to use:
```python
from beir import util
from beir.datasets.data_loader import GenericDataLoader
from beir.retrieval.evaluation import EvaluateRetrieval
```

## Resources

- **GitHub**: github.com/beir-cellar/beir
- **Paper**: Available on arXiv
- **Leaderboard**: Community-maintained rankings

## Pricing

Free and open-source benchmark.