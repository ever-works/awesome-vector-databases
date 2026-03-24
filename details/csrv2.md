## Overview

CSRv2 is a principled training approach designed to make ultra-sparse embeddings viable, stabilizing sparsity learning through progressive k-annealing and enhancing representational quality via supervised contrastive objectives.

## Contrastive Sparse Representation (CSR)

CSR (Contrastive Sparse Representation Learning) combines contrastive retrieval and reconstructive autoencoding objectives to preserve the original feature semantics. CSR takes a pretrained encoding model (with frozen weights), and trains a simple sparse autoencoder on top for mapping the pretrained dense embeddings into a sparse embedding with up to k non-zero elements (i.e., k-sparse).

### Key Benefits

Extensive experiments on image, text, and multimodal benchmarks demonstrate that CSR consistently outperforms MRL in terms of both accuracy and retrieval speed—often by large margins—while also cutting training time to a fraction of that required by MRL. Under the same compute budget, CSR rivals MRL's performance by 9%, 15%, and 7% on ImageNet classification, MTEB text retrieval, and MS COCO retrieval, respectively.

## CSRv2 (2026)

### Major Improvements

- CSRv2 effectively reduces dead neurons from >80% to ~20%
- Delivers a 14% accuracy gain at k=2 compared to prior methods
- Yields up to 300x improvements in compute and memory efficiency relative to dense embeddings and achieves a 7x speedup over Matryoshka Representation Learning (MRL)

### Performance

CSRv2 with only 2 active dimensions matches the performance of Matryoshka Representation Learning (MRL) at 16 dimensions. CSRv2 achieves 7%/4% improvement over CSR when k=4 and further increases this gap to 14%/6% when k=2 in text/vision representation.

The research was published at the 2026 International Conference on Learning Representations (ICLR).

## Pricing

Open-source research implementation.