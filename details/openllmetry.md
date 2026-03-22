## Overview

OpenLLMetry is a set of extensions built on top of OpenTelemetry that provides complete observability over LLM applications. It enables monitoring and debugging through non-intrusive tracing that captures LLM-specific data and metrics.

## LLM-Specific Instrumentation

OpenLLMetry extends OpenTelemetry with AI-aware instrumentation that captures:
- Prompt details and responses
- Token usage and consumption metrics
- Model parameters (temperature, max tokens)
- Specific model versions used
- Execution times and performance data

## Vector Database Support

OpenLLMetry provides custom extensions that instrument vector database calls including:
- **Chroma**: Vector storage and retrieval tracing
- **Pinecone**: Cloud vector database monitoring
- **Qdrant**: Vector search performance tracking
- **Weaviate**: Vector operations observability

## Integration Support

Built-in instrumentations for:
- **LLMs**: OpenAI, Anthropic, Cohere
- **Frameworks**: LangChain, Haystack
- **Vector DBs**: Pinecone, Chroma, Qdrant, Weaviate

## Observability Platform Compatibility

Uses OpenTelemetry protocol to connect with:
- Datadog
- Honeycomb
- Dynatrace
- Custom monitoring solutions

## Multi-Language Support

- Python (main repository)
- TypeScript/JavaScript (openllmetry-js)
- Go (go-openllmetry)
- Ruby (openllmetry-ruby)

## License

Apache 2.0 License