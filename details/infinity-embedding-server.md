## Overview

Infinity is a high-throughput, low-latency REST API serving engine designed for deploying text-embeddings, reranking models, CLIP, CLAP, and ColPali models into production environments.

## Key Features

### GPU Acceleration
- Built on top of torch, optimum (ONNX/TensorRT) and CTranslate2
- Uses FlashAttention for optimal performance on NVIDIA CUDA, AMD ROCM, CPU, AWS INF2, or Apple MPS accelerators
- Multi-GPU support with `--device-id 0,1,2,3` for approximately 4x throughput increase
- Dynamic batching and tokenization in dedicated worker threads

### Docker Deployment
```bash
docker run -it --gpus all \
  -v $volume:/app/.cache \
  -p $port:$port \
  michaelf34/infinity:latest \
  v2 \
  --model-id $model \
  --port $port
```

### Performance Optimization
- Dynamic batching for improved throughput
- Low-latency response times for production workloads
- Efficient tokenization in worker threads
- Support for both CPU and GPU deployments

## Supported Models

- **Text Embeddings**: SentenceTransformers and compatible models
- **Reranking Models**: Cross-encoder models for result reranking
- **CLIP**: Contrastive language-image pretraining models
- **CLAP**: Contrastive language-audio pretraining models
- **ColPali**: Multi-vector retrieval models

## Installation & Deployment

### Docker (Recommended)
- GPU: `michaelf34/infinity:latest`
- CPU: `michaelf34/infinity:latest-cpu`

### CLI Installation
```bash
pip install infinity-emb
infinity_emb v2 --model-id <model> --port <port>
```

### Python API
Use AsyncEmbeddingEngine for programmatic access with maximum flexibility

## API Compatibility

- OpenAI-compatible API specifications
- Swagger UI available at `{url}:{port}/docs` for testing
- RESTful endpoints for easy integration

## Use Cases

- Production embedding services for RAG applications
- Real-time semantic search systems
- Multi-modal search with CLIP/CLAP models
- Reranking services for improved search relevance
- Document retrieval with ColPali

## Pricing

Free and open-source, available on GitHub.