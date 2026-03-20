## Overview

The stella_en model family represents a breakthrough in embedding model distillation, created by researcher dunzhang. These models are distilled from Alibaba's state-of-the-art GTE embedding models using an innovative multi-stage distillation framework.

## Key Innovation: Multi-Stage Distillation

Introduced in the paper "Jasper and Stella: distillation of SOTA embedding models" (arXiv:2412.19048), the approach enables a smaller student embedding model to distill multiple larger teacher embedding models through three carefully designed losses.

### Teacher Models

Stella models are distilled from:
- Alibaba-NLP/gte-large-en-v1.5
- Alibaba-NLP/gte-Qwen2-1.5B-instruct

This multi-teacher approach allows the student model to learn diverse strengths from different architectures.

## Matryoshka Representation Learning (MRL)

Utilizes MRL to support multiple embedding dimensions:
- **512 dimensions**: Compact, fast, lower storage
- **768, 1024 dimensions**: Balanced performance and efficiency
- **2048, 4096 dimensions**: Higher quality for demanding tasks
- **6144, 8192 dimensions**: Maximum quality

**Performance Note**: The MTEB score at 1024d is only 0.001 lower than 8192d, making 1024d a sweet spot for most applications.

## Model Variants

**stella_en_1.5B_v5**: 1.5 billion parameters, higher quality

**stella_en_400M_v5**: 400 million parameters, smaller and faster

Both variants support the full range of dimensions through MRL.

## Simplified Prompting

Stella models simplify prompt usage by providing two prompts for most general tasks:
- **s2p (sentence-to-passage)**: For query-document retrieval
- **s2s (sentence-to-sentence)**: For similarity comparison

This reduces complexity compared to models requiring extensive prompt engineering.

## Performance Benefits

**Competitive Quality**: Through distillation, achieves performance close to much larger teacher models

**Flexible Sizing**: MRL allows trading off quality vs. speed/storage based on application needs

**Efficiency**: Smaller models (400M) offer fast inference while maintaining good quality

## Use Cases

- **High-throughput applications**: Use 512 or 768 dimensions for speed
- **Balanced deployments**: Use 1024 dimensions for optimal quality/efficiency
- **Quality-critical tasks**: Use 4096 or 8192 dimensions
- **Resource-constrained environments**: stella_en_400M_v5 with lower dimensions

## Technical Details

The distillation framework addresses key challenges:
- Efficiently transferring knowledge from multiple large teachers
- Maintaining performance across different embedding dimensions
- Balancing model size reduction with quality preservation

## Availability

Open-source models available on Hugging Face:
- dunzhang/stella_en_1.5B_v5
- dunzhang/stella_en_400M_v5
- Also available through Marqo and other platforms

## Research

Based on "Jasper and Stella: distillation of SOTA embedding models" by Dun Zhang, Jiacheng Li, Ziyang Zeng, and Fulong Wang (2025).