## Overview

GGUF (GPT-Generated Unified Format) is not a quantization technique itself, but a file format for storing quantized models optimized for CPU inference. It's the successor to GGML format and enables running large language models on consumer hardware.

## Features

- **CPU-Optimized**: Designed for efficient CPU inference
- **Hybrid Execution**: Offload layers to GPU for acceleration
- **Multiple Quantization Levels**: Q4_K_M, Q5, Q8, and more
- **Memory Efficient**: Runs on laptops with 8-24GB RAM
- **Cross-Platform**: Works on Mac (including Apple Silicon), Windows, Linux
- **Single File Format**: All model data in one portable file
- **Flexible Precision**: Different quantization levels for speed/quality tradeoffs

## Popular Variants

- **Q4_K_M**: 4-bit quantization, keeps 92% quality (best for Ollama)
- **Q5_K_M**: 5-bit, better quality with slightly larger size
- **Q8_0**: 8-bit, near full quality

## Performance

GGUF Q4_K_M achieves 6.74 perplexity (close to baseline 6.56) while enabling deployment on consumer hardware. Best for CPU deployment and hardware flexibility.

## Use Cases

- Running LLMs on laptops and desktops
- Edge deployment without GPU
- Development and testing locally
- Privacy-focused local AI applications
- Offline AI applications

## Integration

Primary format for Ollama, LM Studio, and llama.cpp. Supported by many local LLM tools.

## Pricing

Free and open-source format. Many pre-quantized GGUF models available on Hugging Face.