## Why RAG Evaluation Matters

RAG systems are complex pipelines with multiple failure modes. Systematic evaluation prevents degradation and ensures quality.

## Key Evaluation Frameworks

**RAGAS** (Retrieval Augmented Generation Assessment):
- Reference-free evaluation using LLMs
- Metrics: context relevance, faithfulness, answer relevancy
- Synthetic test data generation
- Open-source, widely adopted

**TruLens**:
- Feedback functions for programmatic scoring
- In-depth tracing with cost/latency
- OpenTelemetry integration
- Community-driven, now supported by Snowflake

**LangSmith**:
- From LangChain team
- Dataset management
- Human-in-the-loop review
- Production monitoring
- Framework-agnostic

**ARES** (Automated RAG Evaluation System):
- Stanford research project
- Automated evaluation pipelines
- Academic focus

**DeepEval**:
- Python library
- Unit test style for LLMs
- Pytest integration
- Multiple metrics

## Evaluation Metrics

**Retrieval Component**:
- Context Precision: Relevant chunks in top-K
- Context Recall: All needed info retrieved
- Context Relevance: Retrieved docs match query

**Generation Component**:
- Faithfulness: Answer grounded in context
- Answer Relevancy: Addresses the question
- Correctness: Factual accuracy

**End-to-End**:
- RAG Score: Combined metric
- Latency: Response time
- Cost: Token usage

## Evaluation Approaches

**1. LLM-as-Judge**:
- Use GPT-4 to evaluate responses
- Pros: Flexible, no labels needed
- Cons: Expensive, potential bias

**2. Ground Truth Comparison**:
- Compare against reference answers
- Pros: Objective
- Cons: Requires labeled data

**3. Human Evaluation**:
- Expert review of responses
- Pros: Most reliable
- Cons: Slow, expensive

**4. Hybrid Approach**:
- Automated + human spot checks
- Best balance

## Evaluation Workflow

1. **Create Test Set**: Representative queries
2. **Run Pipeline**: Generate responses
3. **Compute Metrics**: Automated scoring
4. **Human Review**: Sample validation
5. **Iterate**: Improve based on results
6. **Monitor Production**: Continuous evaluation

## Best Practices

1. Start with RAGAS for quick setup
2. Build diverse test sets (easy/hard queries)
3. Include edge cases
4. Test multiple query types
5. Monitor metrics over time
6. Set quality thresholds
7. Automate in CI/CD
8. Combine automated + human evaluation

## Common Pitfalls

- Testing only on cherry-picked examples
- Not testing edge cases
- Ignoring latency/cost
- Over-relying on single metric
- Not validating in production

## Framework Comparison

| Framework | Open Source | LLM-as-Judge | Monitoring | Best For |
|-----------|-------------|--------------|------------|----------|
| RAGAS | Yes | Yes | No | Research, Development |
| TruLens | Yes | Yes | Yes | Production Monitoring |
| LangSmith | No | Yes | Yes | LangChain Users |
| DeepEval | Yes | Yes | No | Testing, CI/CD |

## Getting Started

```python
from ragas import evaluate
from ragas.metrics import (
    faithfulness,
    answer_relevancy,
    context_recall,
    context_precision,
)

result = evaluate(
    dataset=eval_dataset,
    metrics=[
        faithfulness,
        answer_relevancy,
        context_recall,
        context_precision,
    ],
)
```