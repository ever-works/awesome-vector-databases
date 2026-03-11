## Overview

LiteLLM is an open-source project that provides a unified interface for working with over 100 LLM providers through a single OpenAI-compatible API. It eliminates the complexity of managing multiple LLM provider SDKs.

## Features

- **Unified API**: Single interface for 100+ LLM providers
- **OpenAI Compatibility**: Drop-in replacement for OpenAI API calls
- **Load Balancing**: Automatic request distribution across providers
- **Fallback Handling**: Automatic failover to backup providers
- **Cost Tracking**: Built-in usage and cost monitoring
- **Caching**: Response caching to reduce costs and latency
- **Rate Limiting**: Configurable rate limits per user or API key
- **Streaming Support**: Full support for streaming responses

## Supported Providers

Supports major providers including OpenAI, Anthropic, Google (PaLM, Gemini), Cohere, Azure OpenAI, AWS Bedrock, Hugging Face, and many more.

## Use Cases

- Building multi-provider LLM applications
- Reducing vendor lock-in
- Cost optimization through provider switching
- High-availability LLM services

## Integration

Integrates with Langfuse for observability and works alongside vector databases in RAG architectures. Popular with developers building production LLM applications.

## Pricing

Free and open-source. The proxy server can be self-hosted or used through LiteLLM's managed service.