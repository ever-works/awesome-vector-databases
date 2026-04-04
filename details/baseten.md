## Overview

Baseten provides GPU inference infrastructure optimized for AI model serving, including embedding models and large language models. The platform offers both cloud-hosted serving and custom client libraries for maximum throughput.

## Key Features

- GPU-accelerated embedding model inference with production-ready performance
- Baseten Performance Client: Custom Rust-based client delivering up to 12x better throughput for batch embedding workloads compared to standard OpenAI SDK implementations
- Containerized model deployment with automatic scaling
- Support for open-source embedding models (E5, BGE, and others)
- Production-grade monitoring and observability

## Performance Client

The Baseten Performance Client is specifically designed for batch embedding workloads, achieving significantly higher throughput than standard HTTP-based SDK clients. This is critical for high-volume embedding pipelines processing millions of documents.

## Pricing

Usage-based pricing model for GPU inference. Specific rates depend on model type, GPU class, and request volume.