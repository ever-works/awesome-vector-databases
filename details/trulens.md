## Overview

TruLens is an open source library for evaluating and tracing AI agents, including RAG systems and other LLM applications. Originally created by TruEra, TruLens is now a community-driven project with active oversight and support from Snowflake following TruEra's acquisition.

## Key Features

### OpenTelemetry Integration

Combines OpenTelemetry-based tracing with trustworthy evaluations, including both ground truth metrics and reference-free (LLM-as-a-Judge) feedback. TruLens instrumentation is OpenTelemetry compatible, allowing interoperation with other observability systems.

### RAG Triad Evaluation

The RAG triad consists of 3 core evaluations:

1. **Context Relevance**: Are retrieved contexts relevant to the query?
2. **Groundedness**: Is the answer grounded in the retrieved context?
3. **Answer Relevance**: Does the answer address the question?

Satisfactory evaluations on each provides confidence that the LLM app is free from hallucination.

### Evaluation Capabilities

Evaluate critical components of your app's execution flow:
- Retrieved context quality
- Tool calls
- Agent plans
- Response generation
- End-to-end performance

## Framework Support

TruLens automatically instruments popular frameworks:

- **TruChain**: For LangChain applications
- **TruGraph**: For LangGraph applications
- **TruLlama**: For LlamaIndex applications
- **Custom Apps**: Flexible instrumentation API

## Installation

```bash
pip install trulens
```

## Basic Usage

```python
from trulens.core import TruSession
from trulens.apps.langchain import TruChain

# Initialize session
session = TruSession()

# Wrap your app
tru_app = TruChain(
    chain,
    app_name="My RAG App",
    app_version="v1"
)

# Use as normal - tracing happens automatically
response = tru_app("What is RAG?")

# View results in dashboard
session.run_dashboard()
```

## Feedback Functions

Define custom evaluation criteria:

```python
from trulens.feedback import Feedback
from trulens.providers.openai import OpenAI

# Initialize provider
provider = OpenAI()

# Define feedback
f_context_relevance = Feedback(
    provider.context_relevance
).on_input().on("context").aggregate(np.mean)
```

## Dashboard

Built-in dashboard for:
- Real-time monitoring
- Trace visualization
- Feedback scores
- Performance metrics
- Comparative analysis

## Key Advantages

- **OpenTelemetry Standard**: Industry-standard tracing
- **Framework Agnostic**: Works with any LLM framework
- **Production Ready**: Built for scale and reliability
- **Comprehensive**: Covers evaluation and tracing
- **Active Development**: Community-driven with enterprise backing

## Use Cases

- RAG system evaluation and debugging
- Agent behavior monitoring
- Multi-turn conversation quality
- Production observability
- Experiment tracking
- A/B testing

## Integration Partners

- LangChain & LangGraph
- LlamaIndex
- Pinecone
- Snowflake
- OpenTelemetry ecosystem

## Resources

- **Documentation**: https://www.trulens.org/
- **GitHub**: https://github.com/truera/trulens
- **Blog**: https://www.trulens.org/blog/
- **Community**: Active Discord

## Pricing

Free and open-source library. Costs only for LLM API calls used in feedback functions.