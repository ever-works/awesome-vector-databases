## Overview

Smolagents is a minimalist AI agent framework developed by Hugging Face that enables developers to run powerful agents in just a few lines of code. The logic for agents fits in approximately 1,000 lines of code, emphasizing simplicity and minimal abstractions.

## Key Features in 2026

**Code-First Approach**: CodeAgent writes its actions in code, as opposed to "agents being used to write code". Instead of generating actions as JSON or text blobs, code agents write and execute Python code snippets to perform tasks.

**Security**: The framework supports executing in sandboxed environments via Blaxel, E2B, Modal, Docker, or Pyodide+Deno WebAssembly sandbox.

**Model Agnostic**: Smolagents supports any LLM, whether a local transformers or ollama model, one of many providers on the Hub, or models from OpenAI, Anthropic and many others via LiteLLM integration.

**Integration**: You can share/pull tools or agents to/from the Hub for instant sharing of the most efficient agents.

## 2026 Context

The Model Context Protocol (MCP) and the smolagents framework are emerging as two architectural pillars that structure AI to be better governed, more isolated, and compatible with real-world DevOps requirements. Retrieved data is processed by a CodeAgent that generates a script (primarily Python), executed in an E2B or Docker sandbox.

Smolagents is described as an ultra-minimal AI agent tools for Python that's easy to read/extend and works with any LLM, making it a popular choice among the top AI agent frameworks in 2026.

## Integrations

- txtai agents are built on top of the smolagents framework
- Support for all LLMs txtai supports (Hugging Face, llama.cpp, OpenAI / Claude / AWS Bedrock via LiteLLM)

## Pricing

Open-source under Apache 2.0 license.