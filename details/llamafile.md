## Overview

llamafile lets you distribute and run LLMs with a single file. It combines llama.cpp with Cosmopolitan Libc into one framework that collapses LLM complexity into a single-file executable that runs locally on most computers with no installation.

## Key Innovation

### Single-File Distribution

- **All-in-One**: Model weights + runtime in one file
- **No Dependencies**: Runs without installation
- **Cross-Platform**: Works on Linux, macOS, Windows
- **Just Run**: Execute file to start LLM

## Architecture

### Components

- **llama.cpp**: Optimized LLM inference engine
- **Cosmopolitan Libc**: Cross-platform C library
- **Model Weights**: Bundled in executable
- **Embedded Server**: Built-in HTTP API

## Embedding Support

### Server Mode with Embeddings

Start embeddings server:
```bash
./model.llamafile --server --nobrowser --embedding
```

### Embedding Models

Available embedding models:
- mxbai-embed-large-v1 (from HuggingFace)
- Custom embedding models
- Any GGUF-format embedding model

### API Endpoint

- **/embedding**: Generate embeddings via HTTP
- OpenAI-compatible API format
- Simple curl/HTTP requests

## Integration

### LangChain

- `LlamafileEmbeddings` class
- Easy integration with RAG pipelines
- Local embedding generation

### LlamaIndex

- Native llamafile support
- Embedding function integration
- Document processing pipelines

### Haystack

- OpenAI-compatible API
- Use with Haystack components
- Local LLM alternative

## Use Cases

### Local AI Applications

- **Privacy-First**: No data sent to cloud
- **Offline Operation**: Works without internet
- **Cost-Free**: No API fees
- **Fast**: Low latency local inference

### Embedding Generation

- RAG systems with local embeddings
- Document vectorization
- Semantic search
- Clustering and classification

### Distribution

- **Simple Deployment**: Copy single file
- **No Installation**: Users just run executable
- **Version Control**: Easy to manage
- **Portability**: Works across systems

## Advantages

### vs Cloud APIs

- No API costs
- Complete privacy
- Offline capability
- No rate limits

### vs Traditional LLM Deployment

- No complex setup
- No dependency hell
- One file distribution
- Instant startup

## Features

- **Embedded HTTP Server**: Built-in API
- **OpenAI Compatibility**: Drop-in replacement
- **Multiple Models**: Support various LLMs
- **Optimized Inference**: llama.cpp performance
- **Resource Efficient**: Optimized memory usage

## Supported Platforms

- Linux (x86_64, ARM64)
- macOS (Intel, Apple Silicon)
- Windows (x86_64)
- FreeBSD
- OpenBSD

## Technical Specifications

- **Format**: GGUF model format
- **Runtime**: llama.cpp
- **Libc**: Cosmopolitan (cross-platform)
- **Server**: Embedded HTTP server
- **APIs**: OpenAI-compatible endpoints

## Development

### Created By

- Mozilla AI
- Open source project
- Active community

### Repository

GitHub: mozilla-ai/llamafile

## Limitations

- File size includes model weights (large files)
- Single model per llamafile
- GPU support platform-dependent
- Memory requirements match model size

## Getting Started

### Basic Usage

1. Download llamafile
2. Make executable
3. Run: `./model.llamafile`
4. Access via browser or API

### Embedding Server

1. Start with --embedding flag
2. Send requests to /embedding endpoint
3. Integrate with your application

## Example Models

Pre-built llamafiles available for:
- Llama models
- Mistral models
- Phi models
- Embedding models

## Pricing

Free and open-source:
- No licensing fees
- No API costs
- Community support
- Infrastructure costs only (if cloud-hosted)