## Overview

ScaNN (Scalable Nearest Neighbors) is a method for efficient vector similarity search at scale, developed by Google Research. It introduces innovative compression techniques and quantization methods to significantly improve search performance.

## Features

- **Anisotropic Vector Quantization**: Unlike traditional quantization, ScaNN prioritizes preserving parallel components between vectors, ideal for Maximum Inner Product Search (MIPS)
- **Three-Phase Search**: Partitioning, scoring with quantized vectors, and rescoring
- **High Performance**: Handles roughly twice as many queries per second for a given accuracy compared to the next-fastest library
- **Open Source**: Available on GitHub with comprehensive documentation
- **Easy Installation**: Install via `pip install scann`

## Algorithms

- Product Quantization with anisotropic loss
- Tree-based partitioning (optional)
- Asymmetric hashing
- SOAR (Spilling with Orthogonality-Amplified Residuals) for improved efficiency

## Use Cases

- Large-scale similarity search
- Recommendation systems
- Image retrieval
- Document search
- Neural search applications

## Pricing

Free and open-source.