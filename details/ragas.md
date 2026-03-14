## Overview

RAGAs (Retrieval-Augmented Generation Assessment) is a framework that provides the necessary ingredients to help you evaluate your RAG pipeline on a component level. Ragas is your ultimate toolkit for evaluating and optimizing Large Language Model (LLM) applications.

## Key Features

### Reference-Free Evaluation

RAGAs started as a framework for "reference-free" evaluation, meaning instead of relying on human-annotated ground truth labels, RAGAs leverages LLMs under the hood to conduct evaluations.

### Component-Level Metrics

**Four Core Metrics**:

1. **Context Relevancy**: Evaluates retrieval component quality
2. **Context Recall**: Measures retrieval completeness
3. **Faithfulness**: Assesses whether answers are grounded in context
4. **Answer Relevancy**: Measures response appropriateness to query

Together, these make up the **RAGAs score**.

### Automatic Test Data Generation

The framework provides tooling for automatic test data generation, reducing the need for manual dataset creation.

## Installation

```bash
pip install ragas
```

## Quick Start

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
        context_precision,
        context_recall,
        faithfulness,
        answer_relevancy,
    ],
)
```

## CLI Interface

```bash
ragas quickstart rag_eval  # Creates RAG evaluation project template
```

## Integration

- **LangChain**: Built-in integration
- **LlamaIndex**: Native support
- **Haystack**: Compatible
- **Custom pipelines**: Flexible API

## LLM Provider Support

- OpenAI
- Anthropic Claude
- Google Gemini
- Azure OpenAI
- Local models via Ollama

## Evaluation Workflow

1. **Prepare Dataset**: Questions, contexts, answers, ground truth
2. **Select Metrics**: Choose relevant evaluation metrics
3. **Run Evaluation**: Execute assessment
4. **Analyze Results**: Review component-level scores
5. **Iterate**: Improve based on insights

## Advantages

- **No Ground Truth Required**: LLM-as-a-judge approach
- **Component-Level Insights**: Separate retriever and generator evaluation
- **Easy Integration**: Works with popular frameworks
- **Automatic Generation**: Test data creation tools
- **Comprehensive**: Covers all RAG aspects

## Use Cases

- RAG pipeline development and optimization
- A/B testing of retrieval strategies
- Embedding model comparison
- Chunk size optimization
- Reranker evaluation
- Production monitoring

## Resources

- **Documentation**: https://docs.ragas.io/
- **GitHub**: https://github.com/vibrantlabsai/ragas
- **PyPI**: https://pypi.org/project/ragas/
- **Tutorials**: Multiple guides available

## Pricing

Free and open-source framework (Apache 2.0 license). Costs only for LLM API calls used in evaluation.