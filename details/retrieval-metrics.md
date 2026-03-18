## Overview

Retrieval metrics are quantitative measures used to evaluate the performance of vector search systems and RAG applications, assessing both the quality of retrieved documents and their relevance to queries.

## Core Retrieval Metrics

**Recall@K**:
- Proportion of relevant items found in top K results
- Critical for ensuring important documents aren't missed
- Formula: Relevant items in top K / Total relevant items

**Precision@K**:
- Proportion of retrieved items that are relevant
- Measures accuracy of top K results
- Formula: Relevant items in top K / K

**Mean Reciprocal Rank (MRR)**:
- Average of reciprocal ranks of first relevant result
- Emphasizes ranking quality
- Higher values indicate relevant results appear earlier

**Normalized Discounted Cumulative Gain (nDCG)**:
- Measures ranking quality with graded relevance
- Accounts for position of relevant documents
- Values from 0 (worst) to 1 (perfect)

## RAG-Specific Metrics

**Context Relevance**:
- Measures relevance of retrieved context to query
- Evaluated using LLM-based scoring

**Context Precision**:
- Proportion of retrieved context actually used in answer
- Reduces noise from irrelevant chunks

**Context Recall**:
- Whether all necessary information was retrieved
- Critical for complete answers

**Faithfulness**:
- Measures if generated answer is grounded in retrieved context
- Detects hallucinations

**Answer Relevancy**:
- Evaluates if answer addresses the question
- End-to-end quality metric

## Benchmark Datasets

- **BEIR**: Diverse IR tasks
- **MTEB**: Massive Text Embedding Benchmark
- **KILT**: Knowledge-Intensive Language Tasks
- **MS MARCO**: Large-scale search dataset

## Evaluation Frameworks

- RAGAS (Retrieval Augmented Generation Assessment)
- TruLens
- LangSmith
- DeepEval

## Trade-offs

- **Recall vs Precision**: Higher recall may reduce precision
- **Latency vs Quality**: More sophisticated ranking takes time
- **Cost vs Accuracy**: Better embeddings/reranking increases cost

## Best Practices

1. Use multiple metrics for comprehensive evaluation
2. Establish baseline performance
3. Test on diverse query types
4. Monitor metrics in production
5. Include human evaluation for quality
6. Track metrics over time for regression detection