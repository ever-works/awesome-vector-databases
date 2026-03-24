## Overview

OpenJarvis is an open-source framework from Stanford's Scaling Intelligence Lab for personal AI agents that run entirely on-device. Released in March 2026, it provides shared primitives for building on-device agents, efficiency-aware evaluations, and a learning loop that improves models using local trace data.

## Key Motivation

Stanford's Intelligence Per Watt research showed that local language models already handle 88.7% of single-turn chat and reasoning queries, with intelligence efficiency improving 5.3× from 2023 to 2025. Traditional personal AI design introduces latency, recurring cost, and data exposure concerns, especially for assistants/agents that operate over personal files, messages, and persistent user context.

## Five Core Primitives

OpenJarvis is structured around five composable primitives:

1. **Intelligence** - The model selection layer that manages the full catalog of local models across providers
2. **Engine** - The inference runtime supporting Ollama, vLLM, SGLang, llama.cpp, cloud APIs, and more, which auto-detects your hardware and recommends the best fit
3. **Agents** - Multi-step reasoning with tool use, featuring seven built-in agent types from simple chat to orchestrated workflows
4. **Tools & Memory** - Web search, calculator, file I/O, code interpreter, retrieval, and any external MCP server
5. **Learning** - Your AI gets better over time, with every interaction generating traces that drive automatic improvements to model weights, prompts, and agent behavior

## Key Features

OpenJarvis prioritizes efficiency, treating energy, FLOPs, latency, and cost as key constraints alongside task quality. It incorporates a hardware-agnostic telemetry system for profiling energy on NVIDIA GPUs, AMD GPUs, and Apple Silicon.

Developer interfaces include a browser application, a desktop application for macOS, Windows, and Linux, a Python SDK, and a command-line interface (CLI), with all core functionality operating without a network connection.

## Pricing

Open-source and free to use under an open-source license.