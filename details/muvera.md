## Overview

MUVERA (MUlti-VEctor Retrieval Algorithm) is a retrieval mechanism which reduces multi-vector similarity search to single-vector similarity search. MUVERA's innovation is to take whole groups of multi-vectors and compress them into a single, easier-to-handle vector called a Fixed Dimensional Encoding (FDE).

## Key Innovation

MUVERA asymmetrically generates Fixed Dimensional Encodings (FDEs) of queries and documents, which are vectors whose inner product approximates multi-vector similarity. FDEs give high-quality ε-approximations, thus providing the first single-vector proxy for multi-vector similarity with theoretical guarantees.

## Performance Benefits

### Retrieval Efficiency
- FDEs achieve the same recall as prior state-of-the-art heuristics while retrieving 2-5× fewer candidates
- Achieves an average of 10% improved recall with 90% lower latency
- Consistently good end-to-end recall and latency across diverse BEIR retrieval datasets

### Data-Oblivious Design
A key advantage of MUVERA is that the FDE transformation is data-oblivious, meaning it doesn't depend on the specific dataset. This makes it:
- Robust to changes in data distribution
- Suitable for streaming applications
- Adaptable to new data without retraining

## Theoretical Foundations

MUVERA provides theoretical guarantees for approximation quality, making it the first single-vector proxy for multi-vector similarity with such guarantees.

## Production Deployment

The research was presented at NeurIPS 2024 and has been implemented in production systems. Weaviate added MUVERA support in version 1.31, demonstrating its practical value for real-world vector search applications.

## Use Cases

- Large-scale semantic search requiring efficiency
- Production systems needing reduced latency
- Applications with streaming data requirements
- Systems requiring both high recall and low latency

## Pricing

Free research from Google, with open implementations available.