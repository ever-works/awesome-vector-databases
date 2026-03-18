## Overview

Mirascope is described as the "LLM Anti-Framework" - a Python toolkit that allows you to use any frontier LLM with one unified interface. It follows a "use-when-you-need" design philosophy, offering modular building blocks you can drop into existing workflows without imposing heavy abstractions.

## Philosophy

Think of Mirascope as the "React" of LLM development, where provider native APIs are HTML/CSS, and agent frameworks are Angular. It provides building blocks for developing LLM-powered applications without unnecessary constraints.

## Features

- **Python-First Approach**: Developing with Mirascope feels like writing regular Python code with native functions and function chaining
- **Unified Interface**: The @llm.call decorator specifies provider and model, allowing you to use LLMs as regular Python functions
- **Response Validation**: Pydantic-based response_model enforces schemas and automatically converts, validates, and constrains model outputs
- **Consistent Streaming**: Unified streaming interface across different LLM providers for real-time response processing
- **Multi-Provider Support**: Works with OpenAI, Anthropic, Google, and other major LLM providers
- **Type Safety**: Built-in type checking and IDE support

## Installation

```bash
pip install mirascope
# or
uv add mirascope
```

## Use Cases

- Building LLM applications without framework lock-in
- Creating agents with real-time feedback
- Integrating multiple LLM providers in a single application
- Developing structured output systems with validation
- Building production-ready RAG pipelines

## Pricing

Free and open-source.