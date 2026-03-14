## Overview

RAG evaluation involves 5 key industry-standard metrics measuring both retriever quality and generator accuracy. These metrics provide a holistic guardrail for reliable RAG pipelines.

## Core Evaluation Metrics

### 1. Answer Relevancy

**Definition**: Measures how relevant the generated response is to the user's question.

**Key Point**: A factually accurate answer that discusses the wrong topic scores poorly on relevancy.

**Evaluation**:
- Does the answer address the actual question?
- Is the response focused and on-topic?
- Are irrelevant details minimized?

**Score**: 0-1 (higher is better)

### 2. Faithfulness

**Definition**: Measures whether the generated response contains hallucinations relative to the retrieved context.

**Key Point**: An answer is faithful if supported entirely by information from the knowledge base.

**Evaluation**:
- Are all statements grounded in retrieved context?
- Any fabricated or inferred information?
- Claims supported by evidence?

**Why It Matters**: Hallucination defeats the entire purpose of retrieval augmentation.

**Score**: 0-1 (higher is better)

### 3. Context Relevance

**Definition**: Measures how relevant the retrieved context is to the input query.

**Evaluation**:
- Is retrieved content pertinent to the question?
- Signal-to-noise ratio in context
- Presence of irrelevant documents

**Impact**: Poor context relevance leads to confused or off-topic answers.

**Score**: 0-1 (higher is better)

### 4. Context Recall

**Definition**: Measures whether the retrieved context contains all information required to produce the ideal output.

**Evaluation**:
- Is sufficient information retrieved?
- Are key facts missing?
- Completeness of context

**Impact**: Low recall means LLM lacks info to answer completely.

**Score**: 0-1 (higher is better)

### 5. Context Precision

**Definition**: Measures whether retrieved context is ranked in the correct order (higher relevancy first).

**Evaluation**:
- Are most relevant docs ranked highly?
- Position of critical information
- Ranking quality

**Impact**: Poor precision wastes context window on less relevant docs.

**Score**: 0-1 (higher is better)

## Metric Relationships

```
RAG Pipeline
    |
    ├── Retriever Quality
    │   ├── Context Relevance (what was retrieved)
    │   ├── Context Recall (completeness)
    │   └── Context Precision (ranking)
    │
    └── Generator Quality
        ├── Answer Relevancy (addresses question)
        └── Faithfulness (no hallucinations)
```

## Evaluation Frameworks

### Ragas (RAG Assessment)

- Automated evaluation using LLMs
- Implements all 5 core metrics
- Integration with LangChain, LlamaIndex

### DeepEval

- Comprehensive RAG testing
- Answer relevancy and faithfulness
- Custom metric definitions

### TruLens

- Real-time evaluation
- Feedback functions
- Debugging capabilities

### Confident AI

- Production monitoring
- Metric tracking
- Continuous evaluation

## Best Practices

1. **Baseline Early**: Establish metric baselines before optimization
2. **Test Systematically**: Create evaluation datasets with ground truth
3. **Monitor Continuously**: Track metrics in production
4. **Balance Trade-offs**: Optimize multiple metrics together
5. **Use LLM Judges**: Leverage models for automated evaluation
6. **Validate with Humans**: Spot-check automated scores

## Typical Benchmarks

| Metric | Poor | Acceptable | Good | Excellent |
|--------|------|------------|------|----------|
| Answer Relevancy | <0.6 | 0.6-0.75 | 0.75-0.85 | >0.85 |
| Faithfulness | <0.7 | 0.7-0.8 | 0.8-0.9 | >0.9 |
| Context Relevance | <0.5 | 0.5-0.7 | 0.7-0.85 | >0.85 |
| Context Recall | <0.6 | 0.6-0.75 | 0.75-0.85 | >0.85 |
| Context Precision | <0.6 | 0.6-0.75 | 0.75-0.85 | >0.85 |

## Common Issues and Solutions

**Low Answer Relevancy**:
- Improve prompt engineering
- Better query reformulation
- Tune LLM parameters

**Low Faithfulness**:
- Stronger grounding instructions
- Citation requirements
- Reduce temperature

**Low Context Relevance**:
- Improve embedding model
- Better chunking strategy
- Hybrid search

**Low Context Recall**:
- Increase top-k retrieval
- Multi-query retrieval
- Query expansion

**Low Context Precision**:
- Add reranker
- Improve embedding quality
- Better metadata filtering

## Tools and Libraries

- **Ragas**: https://docs.ragas.io/
- **DeepEval**: https://deepchecks.com/
- **TruLens**: https://www.trulens.org/
- **LangSmith**: LangChain evaluation
- **Phoenix**: Arize AI evaluation

## Pricing

Most evaluation frameworks are free and open-source, with commercial options for production monitoring.