## Overview

Re2G is a system published at NAACL 2022 that blends symbolic and neural retrieval via reranking layers, combining neural initial retrieval and reranking into a BART-based sequence-to-sequence generation pipeline.

## Architecture

**Multi-stage Approach**:
1. Initial retrieval phase creates candidate document pool
2. One or more reranking phases with increasingly sophisticated models
3. Final generation conditioned on reranked results

## Key Features

- **Ensemble Capability**: Reranking permits merging retrieval results from sources with incomparable scores, enabling BM25 and neural retrieval ensembles
- **End-to-End Training**: Novel knowledge distillation variation trains retrieval, reranker, and generation using only ground truth target sequences
- **State-of-the-Art Performance**: Achieved 9-34% relative gains over previous SOTA on KILT leaderboard

## Performance

Demonstrated large gains across four diverse tasks:
- Zero-shot slot filling
- Question answering
- Fact-checking
- Dialog systems

## Technical Innovation

Builds on RAG and REALM models, addressing knowledge-intensive tasks where non-parametric memory allows models to scale dramatically with sub-linear increases in computational cost and GPU memory.

## Availability

Open-source code available on GitHub. Reranker models available on Hugging Face (ibm-research/re2g-reranker-trex).

## Publication

NAACL 2022, authored by Michael Glass, Gaetano Rossiello, and colleagues from IBM Research.

## Pricing

Research paper and code - free and open-source.