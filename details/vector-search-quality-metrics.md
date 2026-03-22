## Overview

Vector search quality metrics quantify retrieval performance, enabling systematic optimization and comparison. These metrics help tune parameters, select models, and validate improvements.

## Core Metrics

### Recall@k
Fraction of relevant items in top-k results:
```
Recall@k = (# relevant in top-k) / (total # relevant)
```

**Interpretation:**
- 100% = Found all relevant items
- Higher = Better
- k typical values: 1, 5, 10, 100

**Use Cases:**
- ANN algorithm evaluation
- Parameter tuning
- Model comparison

### Precision@k
Fraction of top-k that are relevant:
```
Precision@k = (# relevant in top-k) / k
```

**Interpretation:**
- 100% = All returned items relevant
- Important when k is small
- Complements recall

### Mean Reciprocal Rank (MRR)
Average reciprocal rank of first relevant result:
```
MRR = (1/n) × Σ(1/rank_i)
```

**Interpretation:**
- 1.0 = First result always relevant
- 0.5 = Average rank of 2
- Emphasizes top results

**Use Cases:**
- Question answering
- Single-answer queries
- RAG systems

### Normalized Discounted Cumulative Gain (NDCG@k)
Considers both relevance and position:
```
DCG@k = Σ(relevance_i / log2(i + 1))
NDCG@k = DCG@k / Ideal_DCG@k
```

**Interpretation:**
- 1.0 = Perfect ranking
- Discounts lower positions
- Gold standard for ranking

**Use Cases:**
- Graded relevance (not binary)
- Ranking quality
- Search engines

### Mean Average Precision (MAP)
Mean of average precision across queries:
```
AP = (1/R) × Σ(Precision@k × rel_k)
MAP = (1/Q) × Σ AP_q
```

**Interpretation:**
- Considers precision at all positions
- Comprehensive metric
- Standard in IR research

## RAG-Specific Metrics

### Context Relevance
How relevant is retrieved context to query?
- LLM-judged (0-1 scale)
- Automated with prompt
- Correlates with answer quality

### Context Utilization
Does LLM actually use the context?
- Check if answer uses retrieved facts
- Attribution analysis
- Measures retrieval necessity

### Answer Correctness
Final answer quality:
- Exact match (for factual QA)
- LLM-as-judge scoring
- Human evaluation
- BLEU/ROUGE (for generation)

### Faithfulness
Does answer align with context?
- No hallucination metric
- LLM checks contradiction
- Critical for trust

### End-to-End Latency
Total response time:
- Embedding generation
- Vector search
- LLM inference
- Target: <2s typical

## Evaluation Frameworks

### RAGAS (RAG Assessment)
Comprehensive RAG evaluation:
- Context precision
- Context recall
- Faithfulness
- Answer relevance

### ARES
Automated evaluation:
- Prediction-powered inference
- Context relevance
- Answer faithfulness
- Answer relevance

### TruLens
Observability and evaluation:
- Groundedness
- Answer relevance
- Context relevance
- Custom metrics

## Benchmarking Process

### 1. Create Eval Dataset
- Collect representative queries
- Label relevant documents
- Include edge cases
- Minimum 50-100 queries

### 2. Define Metrics
- Choose appropriate metrics
- Set target thresholds
- Consider trade-offs

### 3. Baseline
- Measure current performance
- Establish reference point
- Document configuration

### 4. Iterate
- Test variations
- Measure impact
- Compare to baseline
- Track improvements

### 5. Validate
- A/B test in production
- User feedback
- Monitor over time

## Tools & Implementation

### Python Libraries
```python
from sklearn.metrics import (
    ndcg_score,
    average_precision_score
)
import numpy as np

# Calculate recall@k
def recall_at_k(relevant, retrieved, k):
    retrieved_k = retrieved[:k]
    return len(set(relevant) & set(retrieved_k)) / len(relevant)
```

### Commercial Tools
- Arize AI (ML observability)
- WhyLabs (data quality)
- TruEra (model quality)

## Best Practices

1. **Multiple Metrics**: No single metric tells full story
2. **Representative Data**: Eval set must match production
3. **Continuous Evaluation**: Monitor metrics over time
4. **User Metrics**: Combine with click-through, satisfaction
5. **Cost-Quality Trade-off**: Balance metrics with latency/cost

## Common Pitfalls

### Overfitting to Metrics
- Optimize for real user value
- Metrics are proxies
- Validate with humans

### Small Eval Sets
- Need sufficient queries
- Statistical significance
- Confidence intervals

### Static Evaluation
- Production data shifts
- Monitor continuously
- Update eval sets

## Pricing

Evaluation costs depend on LLM-based judging and dataset size.