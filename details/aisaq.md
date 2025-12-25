---
title: AiSAQ
slug: aisaq
category: Research Papers & Surveys
tags:
  - ann
  - similarity-search
  - vector-indexing
source_url: https://arxiv.org/pdf/2404.06004.pdf
featured: false
---

## Overview

**AiSAQ (All-in-Storage ANNS with Product Quantization)** is a research method for approximate nearest neighbor search (ANNS) that places compressed vectors entirely on SSD, enabling **DRAM-free (or near-DRAM-free) vector similarity search** at billion-scale. It builds on DiskANN, modifying how product-quantized vectors are stored and accessed to drastically cut RAM usage while maintaining high recall and practical latency.

## Key Details

- **Type:** Research paper / algorithmic method
- **Domain:** Large-scale vector search, information retrieval, RAG backends
- **Core idea:** Offload PQ-compressed vectors from DRAM into SSD-based indices, so memory usage no longer scales with dataset size.
- **Code:** DiskANN-based implementation available on GitHub: https://github.com/KioxiaAmerica/aisaq-diskann

## Features

- **All-in-storage PQ design**
  - Compressed (product-quantized) node vectors are stored on SSD instead of being kept in DRAM.
  - Breaks the proportional relationship between DRAM usage and dataset size.

- **Extremely low DRAM footprint**
  - Achieves on the order of ~10 MB memory usage for query search on **billion-scale** vector datasets (as reported in the paper abstract).
  - Suitable for environments where DRAM is costly or limited.

- **Based on DiskANN**
  - Uses DiskANN as the underlying graph-based ANNS framework.
  - Preserves the graph-search paradigm and re-ranking strategy, but changes where/how compressed vectors are stored.

- **Product Quantization (PQ) for compression**
  - Employs PQ to represent high-dimensional vectors compactly.
  - Relieves the DiskANN trade-off where increasing compression lowers both memory use and recall, by moving PQ data to storage.

- **Maintains recall–latency balance**
  - Designed to achieve **DRAM-free** or near-DRAM-free search **“without critical latency degradation”** compared to standard DiskANN setups.
  - Still uses full-precision vectors from storage for re-ranking along the search path.

- **Fast index switching**
  - Reduces index load time required before queries can be served.
  - Makes it practical to **switch rapidly between multiple billion-scale indices**, useful when many vector collections must be queried selectively.

- **Suitable for RAG (Retrieval-Augmented Generation)**
  - Can act as a retriever backend for LLM-based RAG systems.
  - Multiple external knowledge sources can be stored as separate indices and switched on demand, without loading all index data into RAM.

- **Scalability and multi-server deployment**
  - Intended to scale out across **multiple-server systems** for emerging, very large datasets.
  - SSD-based index design fits distributed or sharded deployments.

- **Use with vector database systems**
  - Conceptually related to existing DiskANN-based services used in vector databases such as Weaviate and Zilliz (mentioned as context in the paper).

## Use Cases

- Large-scale image, music, or document retrieval where dataset size reaches **billions of vectors**.
- RAG systems that:
  - Need to query multiple knowledge bases / indices.
  - Require fast index switching without reloading large indices into DRAM.
- Cost-sensitive deployments where minimizing DRAM footprint is essential while still needing high-quality ANN search.

## Pricing

- This is a **research method / open implementation**, not a commercial product. 
- No pricing or commercial plans are specified in the paper content.
