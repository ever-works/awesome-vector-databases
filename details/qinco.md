# Qinco

**Brand:** Meta AI Research  
**Category:** SDKs & Libraries  
**Source:** [GitHub – facebookresearch/Qinco](https://github.com/facebookresearch/Qinco)

Qinco (and its improved variant QINCo2) is an open‑source, neurally‑augmented residual quantization system for compact vector representations. It is designed as a low-level component for vector indexing, compression, and large‑scale similarity / nearest neighbor search.

---

## Overview

Qinco implements **Quantization with Implicit Neural Codebooks (QINCo)** and its successor **QINCo2: Vector Compression and Search with Improved Implicit Neural Codebooks**. It targets multi‑codebook vector quantization—specifically residual quantization (RQ)—to compress high‑dimensional vectors while maintaining accuracy for similarity and nearest neighbor retrieval at scale.

The repository includes:
- QINCo2 (latest implementation and improvements)
- QINCo1 (original ICML 2024 implementation, under `qinco_v1`)

---

## Features

### Core Quantization Approach
- **Neurally-augmented multi‑codebook vector quantization**
  - Implements residual quantization (RQ) with learned implicit neural codebooks.
  - Replaces fixed codebooks at each quantization step with a neural network that predicts the next codebook conditioned on the already‑quantized prefix of the vector.
- **Implicit neural codebooks conditioned on Voronoi cells**
  - Codebooks depend on previously selected Voronoi cells, increasing the expressive capacity of the compression without storing large explicit codebooks.
- **Dynamic rate quantization**
  - Each quantization step is trained with its own quantization error objective.
  - A trained system for a given compression rate can also be used at lower compression rates, enabling flexible trade‑offs between compression and accuracy.

### QINCo2 Improvements over QINCo1
- **Fast approximate encoding**
  - New approximate encoding procedure.
  - Achieves similar mean squared error (MSE) as the original method.
  - Significantly reduces training and encoding time.
- **Beam search integration in encoding**
  - Adds beam search to the encoding pipeline.
  - When combined with approximate encoding, achieves much lower compression error than QINCo1 at similar encoding time.
- **Optional pairwise decoder module for retrieval**
  - New (optional) module in the large‑scale retrieval pipeline.
  - Uses a pairwise decoder to improve retrieval accuracy.
- **Architecture and training pipeline upgrades**
  - Overall improvements to the model architecture.
  - Refined training process for better compression and search performance.

### Large-Scale Retrieval & Search
- **Designed for similarity and nearest neighbor search**
  - Produces compact vector representations suitable for approximate nearest neighbor (ANN) search.
  - Targets large-scale datasets and vector databases / AI retrieval systems.
- **Integration into retrieval pipelines**
  - Supports large‑scale vector indexing and retrieval scenarios.
  - Optional pairwise decoder can be added to improve search quality.

### Data & Experiment Support
- **Reference datasets and scripts**
  - Download scripts for common large-scale benchmarks:
    - **BigANN** (with `-small` option for reduced storage use)
    - **Deep1B** (with `-small` option)
    - **Contriever**
    - **FB-ssnpp**
- **Pretrained checkpoints (base experiments)**
  - Checkpoints provided for QINCo1 and QINCo2 base experiments (as referenced in the repository).

### Implementation & Setup
- **Open-source Python implementation**
  - Requires Python 3.
  - Dependencies managed via `environment.yml` / `requirements.txt`.
- **Conda-based environment setup**
  - Example workflow:
    - `git clone https://github.com/facebookresearch/Qinco` (or updated repo path as in docs)
    - `cd Qinco`
    - `conda env create -f environment.yml`

### Research Orientation
- **Reproducible research code**
  - Includes code to reproduce results from:
    - ICML 2024 paper: *Residual Quantization with Implicit Neural Codebooks* (QINCo1).
    - ICLR 2025 paper: *QINCo2: Vector Compression and Search with Improved Implicit Neural Codebooks*.
- **Citable resource**
  - Provided BibTeX entry for citing QINCo2 in research.

---

## Use Cases

- As a **low-level quantization and indexing component** for:
  - Vector databases.
  - Large-scale AI retrieval and recommendation systems.
  - Embedding-based search in NLP, CV, and multimodal applications.
- For **research and experimentation** on:
  - Neural vector quantization methods.
  - Compression–accuracy trade‑offs in large‑scale ANN search.

---

## Pricing

- **Open-source**: No pricing information is listed; the project is distributed as open-source research code on GitHub.

---

## Tags

- `vector-compression`
- `similarity-search`
- `open-source`