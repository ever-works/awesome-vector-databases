## Overview

Cross-Encoder Reranking is a two-stage retrieval approach where fast approximate search provides candidates, which are then reranked using slower but more accurate cross-encoder models.

## Two-Stage Process

### Stage 1: Candidate Retrieval
- Use bi-encoder for fast similarity search
- Retrieve top-k candidates (e.g., k=100)
- Low cost, high recall
- Millisecond latency

### Stage 2: Reranking
- Pass query+candidate pairs to cross-encoder
- Model scores each pair jointly
- High accuracy
- Return top-n (e.g., n=10)

## Why It Works

Bi-encoders encode query and document separately, limiting interaction. Cross-encoders encode them together, capturing fine-grained relationships but at higher computational cost.

## Implementation in Hindsight

Hindsight uses four parallel retrieval strategies, then applies cross-encoder reranking to combine and refine results, achieving 91.4% on LongMemEval.

## Popular Cross-Encoders

- BGE Reranker models
- Cohere Rerank
- Cross-encoder/ms-marco models
- Custom fine-tuned models

## Performance Trade-offs

- **Accuracy**: 10-30% improvement over bi-encoder alone
- **Latency**: Adds 50-200ms
- **Cost**: Higher compute requirements
- **Scalability**: Limited by reranking budget

## Best Practices

- Limit reranking to top-100 candidates
- Use GPUs for cross-encoder inference
- Batch reranking requests
- Cache results when possible

## Pricing

Technique/pattern, various implementations available.