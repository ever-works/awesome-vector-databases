---
title: LibVQ
slug: libvq
category: sdks-libraries
source_url: https://github.com/staoxiao/LibVQ
images:
  - https://opengraph.githubassets.com/1/staoxiao/LibVQ
tags:
  - vector-quantization
  - neural-search
  - ann
---

## Description
LibVQ is an open-source library for dense-retrieval–oriented vector quantization. It provides training and indexing components that optimize vector quantization for retrieval quality, and can serve as the core of high-performance approximate nearest neighbor (ANN) search and vector database systems.

## Features
- **Dense retrieval–oriented vector quantization**
  - Designed specifically to improve retrieval quality compared with conventional VQ methods (e.g., IVF, PQ, OPQ).
  - Targets real-time and memory-efficient dense retrieval scenarios.

- **Knowledge distillation–based learning**
  - Uses knowledge distillation to learn VQ parameters from off-the-shelf embeddings.
  - Can directly operate on existing dense embeddings without modifying upstream models.
  - Aims to achieve strong retrieval metrics (e.g., MRR@10, Recall@10/100) compared to other VQ-based ANN indexes.

- **Flexible usage modes**
  - Train only VQ/index parameters while keeping encoders fixed.
  - Jointly adapt and train the query encoder together with the index.
  - Supports different training strategies (e.g., contrastive index training, distillation-based index training).

- **Rich input condition support**
  - Works with only off-the-shelf embeddings when no extra signals are available.
  - Optionally leverages extra supervision such as:
    - Relevance labels.
    - Source queries.
  - Can be configured for both labeled and no-label (unlabeled) training settings.

- **PyTorch-based training**
  - Training pipeline implemented with PyTorch.
  - Configurable for different computation resources and training setups.

- **FAISS-backed ANN deployment**
  - Exports trained VQ parameters to FAISS-based indexes (e.g., `IndexPQ`, `IndexIVFPQ`).
  - Resulting indexes are directly deployable for large-scale dense retrieval.
  - Integrates with common ANN backends similar to FAISS, ScaNN, etc.

- **Example workflows and benchmarks**
  - Example pipelines for constructing and training indexes (documented in the `Docs` and `examples` folders).
  - MSMARCO example demonstrating:
    - IVFPQ and PQ settings with a fixed compression ratio (e.g., 96x compression).
    - Multiple training recipes, including:
      - `contrastive_index`
      - `distill_index`
      - `distill_index_nolabel`
      - `contrastive_index-and-query-encoder`
      - `distill_index-and-query-encoder`
      - `distill_index-and-query-encoder_nolabel`
    - Reported metrics such as MRR@10, Recall@10, Recall@100 for these methods and for baseline FAISS/ScaNN indexes.

- **Simple installation from source**
  - Installable via `pip` after cloning the repository:
    - `git clone https://github.com/staoxiao/LibVQ.git`
    - `cd LibVQ`
    - `pip install .`

## Installation
```bash
git clone https://github.com/staoxiao/LibVQ.git
cd LibVQ
pip install .
```

## Pricing
LibVQ is an open-source library; no pricing information or paid plans are specified.
