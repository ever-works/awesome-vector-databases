## Overview

GPTQ (Generative Pre-trained Transformer Quantization) is a pioneering post-training quantization method that compresses large language models to 4-bit precision while maintaining accuracy. It was the first method to successfully compress LLMs to the 4-bit range.

## Features

- **4-Bit Quantization**: Compresses model weights to 4-bit precision
- **GPU-Optimized**: Designed specifically for fast GPU inference
- **Accuracy Preservation**: Minimizes mean squared error to maintain model quality
- **Post-Training**: No fine-tuning required, works on pre-trained models
- **Memory Reduction**: 4x reduction in model size compared to FP16
- **Fast Inference**: Optimized for high-throughput GPU serving

## Performance

Provides significant speedup for GPU inference while maintaining model quality close to the original precision.

## Use Cases

- Deploying large models on consumer GPUs
- Reducing inference costs in production
- Running larger models within memory constraints
- High-throughput GPU serving

## Comparison

- **vs AWQ**: GPTQ is faster but AWQ preserves slightly more accuracy
- **vs GGUF**: GPTQ is GPU-focused, GGUF is CPU/hybrid-focused
- **vs FP16**: 4x smaller with minimal quality loss

## Integration

Supported by Hugging Face Transformers, vLLM, and other LLM serving frameworks. Models quantized with GPTQ can be easily loaded and deployed.

## Pricing

Free and open-source method. Pre-quantized models available on Hugging Face.