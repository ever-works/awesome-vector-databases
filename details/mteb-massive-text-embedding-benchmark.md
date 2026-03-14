## Overview

MTEB (Massive Text Embedding Benchmark) is a comprehensive benchmark suite for evaluating embedding models across diverse NLP tasks like retrieval, classification, clustering, reranking, and semantic similarity.

## Coverage

- **58 datasets** across multiple domains
- **112 languages** for multilingual evaluation
- **8 task types**:
  1. Retrieval
  2. Clustering
  3. Semantic Textual Similarity (STS)
  4. Classification
  5. Reranking
  6. Pair Classification
  7. Bitext Mining
  8. Summarization

## Evaluation Metrics

### Task-Appropriate Metrics

- **Retrieval**: nDCG@10, Recall@K
- **Similarity**: Spearman correlation
- **Clustering**: Normalized Mutual Information (NMI)
- **Classification**: Accuracy, F1-score

### Retrieval Process

1. Embed queries and documents
2. Rank documents using cosine similarity
3. Score with nDCG@10

## BEIR Integration

MTEB directly uses the open source benchmark BEIR in its retrieval part, which contains 15 datasets covering:
- Scientific papers (SCIDOCS)
- Question answering (Natural Questions)
- Fact verification (FEVER)
- News (TREC NEWS)
- Biomedical (TREC COVID)
- Argumentative search

## Leaderboard

MTEB maintains a public leaderboard showing:
- Overall scores across all tasks
- Task-specific performance
- Multilingual capabilities
- Model rankings

Top models include:
- NVIDIA NV-Embed-v2
- Cohere embed-v4
- Jina embeddings-v3
- OpenAI text-embedding-3-large

## Practical Usage Workflow

1. **Screening**: Use MTEB for fast model filtering (e.g., >60 on retrieval)
2. **Robustness Check**: Run BEIR to verify domain transfer
3. **Production Validation**: Test on labeled production data
4. **A/B Testing**: Deploy and measure real-world performance

## Evaluation with MTEB

```python
from mteb import MTEB
from sentence_transformers import SentenceTransformer

model = SentenceTransformer("model-name")
evaluation = MTEB(tasks=["Banking77Classification"])
results = evaluation.run(model)
```

## Why MTEB Matters

- **Standardized Comparison**: Fair comparison across models
- **Comprehensive Coverage**: Multiple tasks and languages
- **Community Standard**: Industry-wide adoption
- **Reproducibility**: Consistent evaluation methodology
- **Model Selection**: Data-driven model choice for RAG and search

## Limitations

- May not reflect specific domain performance
- Benchmark tasks may not match production use cases
- Static datasets may become outdated
- High scores don't guarantee production success

## Resources

- **GitHub**: https://github.com/embeddings-benchmark/mteb
- **Hugging Face**: https://huggingface.co/mteb
- **Leaderboard**: https://huggingface.co/spaces/mteb/leaderboard
- **Documentation**: https://embeddings-benchmark.github.io/mteb/

## Integration

- Sentence Transformers
- Hugging Face
- Evaluation frameworks
- Research papers

## Pricing

Free and open-source benchmark framework.