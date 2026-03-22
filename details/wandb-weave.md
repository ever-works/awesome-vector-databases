## Overview

W&B Weave is Weights & Biases' LLM observability platform that provides automatic tracking of every LLM call, enabling developers to monitor, debug, and optimize AI applications in both development and production.

## Automatic Tracking

Using the `@weave.op` decorator, Weave automatically captures:
- All inputs and outputs
- Costs and token usage
- Latency metrics
- Evaluation results
- Model versions and configurations

## Prompt Engineering Support

Weave provides:
- Tracking and logging of different prompts
- Performance visualization and comparison
- Side-by-side experiment comparison
- Prompt optimization insights
- A/B testing capabilities

## Experiment Tracking

- Track every model, metric, and hyperparameter
- Full visibility into AI workflow
- Reproduce results with saved configurations
- Git commit tracking
- Model weights versioning
- Sample test predictions logging

## Tracing and Monitoring

- Granular-level logging of inputs, outputs, code, and metadata
- Visualization of LLM call traces
- Debug issues during development
- Monitor agents and AI applications in production

## Integration Ecosystem

- **LLM Frameworks**: LangChain, LlamaIndex
- **ML Frameworks**: PyTorch, HuggingFace Transformers
- **Vector Stores**: Integrated through LangChain and LlamaIndex

## Enterprise Features

- Centralized dashboard for all experiments
- Cost tracking and optimization
- Team collaboration tools
- Model performance comparison