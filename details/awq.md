## Overview

AWQ (Activation-aware Weight Quantization) is an advanced quantization technique that recognizes not all weights are equally important for LLM performance. It selectively preserves critical weights while quantizing others to 4-bit precision.

## Features

- **Activation-Aware**: Identifies important weights based on activation patterns
- **Selective Quantization**: Skips critical weights to preserve accuracy
- **4-Bit Compression**: Reduces model size to 25% of original
- **High Accuracy**: Typically maintains 99%+ of original model performance
- **GPU-Friendly**: Optimized for GPU inference
- **Better Preservation**: Often outperforms GPTQ on accuracy metrics

## Performance

AWQ excels at preserving model accuracy at 4-bit quantization, with recent benchmarks showing it retains 95% quality compared to GPTQ's lower retention. Marlin-AWQ achieves 741 tok/s throughput with 51.8% Pass@1 on coding tasks.

## Use Cases

- Applications where accuracy is critical
- Production deployments requiring quality preservation
- Running larger models on limited GPU memory
- Balanced speed-accuracy tradeoffs

## Comparison

- **vs GPTQ**: Better accuracy preservation, slightly slower
- **vs GGUF**: GPU-focused, higher quality retention
- **vs Full Precision**: 4x smaller with minimal quality loss

## Integration

Supported by vLLM, TGI (Text Generation Inference), and Hugging Face Transformers. Pre-quantized AWQ models readily available.

## Pricing

Free and open-source. Many pre-quantized models available on Hugging Face.