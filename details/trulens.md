## Overview

TruLens is an open-source platform for evaluating and monitoring LLM applications, with specialized capabilities for RAG systems. It pioneered the "RAG Triad" evaluation framework that's become an industry standard.

## Features

- **RAG Triad Metrics**: Groundedness, answer relevance, and contextual relevance
- **Feedback Functions**: Programmatic evaluation of application components
- **Trace Visualization**: Detailed execution flow tracking
- **LLM-as-Judge**: Use LLMs to evaluate other LLM outputs
- **Component-Level Evaluation**: Assess individual parts of RAG pipelines
- **Real-Time Monitoring**: Track application performance in production
- **Custom Metrics**: Define your own evaluation criteria
- **Integration**: Works with major LLM frameworks

## RAG Triad

1. **Groundedness**: Whether the answer is factually consistent with the retrieved context
2. **Answer Relevance**: How relevant the generated answer is to the query
3. **Context Relevance**: How relevant the retrieved context is to the query

## Use Cases

- Evaluating RAG system accuracy
- Debugging hallucination issues
- Monitoring production AI applications
- A/B testing different prompts or models
- Ensuring response quality

## Integration

Supports LangChain, LlamaIndex, and custom applications. MLflow's third-party scorer framework includes TruLens alongside RAGAS and Phoenix.

## Pricing

Open-source and free to use.