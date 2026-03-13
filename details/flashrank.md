## Overview

FlashRank is an ultra-lite and super-fast Python library to add re-ranking to your existing search & retrieval pipelines. It is based on SoTA LLMs and cross-encoders, created by Prithiviraj Damodaran.

## Key Features

### Lightweight Design

- No Torch or Transformers needed
- Runs on CPU
- Boasts the tiniest reranking model in the world, ~4MB
- ONNX-optimized for very fast performance on CPU

### Model Support

Supports SoTA Listwise and Pairwise reranking:
- Cross-encoder based pairwise/pointwise rerankers (Max tokens = 512)
- LLM-based listwise rerankers (Max tokens = 8192)

## Performance Benefits

- Designed as a very lightweight and fast reranking library
- Leverages smaller, optimized transformer models (often distilled or pruned versions)
- Lowest $ per invocation for serverless deployments
- Shorter cold start times and quicker re-deployments
- Smaller package size reduces Lambda/serverless costs

## Integration

FlashRank integrates with various frameworks including:
- LangChain
- The rerankers library
- Custom search pipelines

## Use Cases

- Improving search relevance in RAG systems
- Re-ranking retrieval results
- Production deployments where cost and latency matter
- Serverless and edge computing environments

## Pricing

Free and open-source, available on GitHub and PyPI.