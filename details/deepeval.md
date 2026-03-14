## Overview

DeepEval offers 50+ SOTA (state-of-the-art), ready-to-use metrics for evaluating large language models. Almost all predefined metrics on deepeval use LLM-as-a-judge, with various techniques such as QAG (question-answer-generation), DAG (deep acyclic graphs), and G-Eval to score test cases.

## Key Metric Categories

### RAG Evaluation Metrics

- **Faithfulness**: Evaluate whether output factually aligns with retrieval context
- **Contextual Recall**: Measure how well retrieval context aligns with expected output
- **Contextual Precision**: Evaluate whether relevant nodes are ranked higher
- **Contextual Relevancy**: Measure overall relevance of retrieval context
- **RAGAS**: Average of answer relevancy, faithfulness, contextual precision, and recall

### Multi-turn Conversation Metrics

For chatbots and conversational AI:

- **Knowledge Retention**: Does chatbot retain factual information throughout conversation?
- **Conversation Completeness**: Are user needs satisfied throughout conversation?
- **Turn Relevancy**: Are responses consistently relevant throughout conversation?

### Agentic Metrics

Evaluates overall execution flow of your agent:
- Task completion metrics
- Tool usage evaluation
- Plan quality assessment
- Multi-step reasoning

### Custom Metrics

**G-Eval**: Framework using LLM-as-a-judge with chain-of-thoughts (CoT) to evaluate outputs based on ANY custom criteria. Most versatile metric deepeval offers, capable of evaluating almost any use case with human-like accuracy.

**DAG Metric**: For extremely deterministic metric scores, allows evaluation by constructing LLM-powered decision trees.

## Scoring System

All metric scores range from 0 - 1:
- threshold=0.5 determines if test passed
- Customizable thresholds per metric
- Clear pass/fail indicators

## Installation

```bash
pip install deepeval
```

## Quick Start

```python
from deepeval import evaluate
from deepeval.metrics import AnswerRelevancyMetric
from deepeval.test_case import LLMTestCase

# Define test case
test_case = LLMTestCase(
    input="What is RAG?",
    actual_output="RAG is...",
    retrieval_context=["Context 1", "Context 2"]
)

# Define metric
metric = AnswerRelevancyMetric(threshold=0.7)

# Evaluate
evaluate([test_case], [metric])
```

## Features

- **Plug-and-use**: 50+ LLM-evaluated metrics with research backing
- **Multi-modal**: All metrics support multi-modal evaluation
- **Versatile**: RAG, agents, chatbots, and virtually any use case
- **Component-level**: Both end-to-end and component level evaluation
- **Customizable**: G-Eval for custom criteria

## Advanced Capabilities

- **Pytest Integration**: Run evaluations as unit tests
- **Benchmarking**: Compare models and prompts
- **Continuous Evaluation**: CI/CD integration
- **Dataset Management**: Built-in test case organization
- **Reporting**: Comprehensive evaluation reports

## Use Cases

- RAG pipeline testing
- Agent behavior validation
- Chatbot quality assurance
- Model comparison
- Regression testing
- Production monitoring

## Integration

- LangChain
- LlamaIndex
- OpenAI
- Anthropic
- Custom LLM applications

## Confident AI Platform

DeepEval integrates with Confident AI platform for:
- Production monitoring
- Team collaboration
- Advanced analytics
- Historical tracking

## Resources

- **Documentation**: https://deepeval.com/docs/
- **GitHub**: https://github.com/confident-ai/deepeval
- **Tutorials**: Multiple guides on DataCamp, Codecademy
- **Platform**: https://www.confident-ai.com/

## Pricing

- **Open Source**: Free deepeval framework
- **Confident AI**: Commercial platform with additional features
- **LLM Costs**: Pay for API calls used in evaluations