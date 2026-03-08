## Overview

MTEB (Massive Text Embedding Benchmark) is a massive benchmark for measuring the performance of text embedding models on diverse embedding tasks. MTEB spans 8 embedding tasks covering a total of 58 datasets and 112 languages.

## Expansion: MMTEB

MMTEB (Massive Multilingual Text Embedding Benchmark) expands MTEB to over 500 quality-controlled evaluation tasks across 1,000+ languages, making it the most comprehensive multilingual embedding benchmark.

## Current Top Models (2025-2026)

### gte-Qwen3-8B
- Largest of a family of new embedding models built on top of Qwen3
- Outperforms previous generation Qwen embedding models
- Ranks high on both multi-lingual and English-only MTEB leaderboards

### NV-Embed-v2 (NVIDIA)
- Released October 2025
- Fine-tuned from Llama-3.1-8B
- Particularly powerful at understanding multilingual text
- Previous version (NV-Embed) achieved score of 69.32 on MTEB (56 embedding tasks)

## Benchmark Tasks

MTEB covers 8 main embedding tasks:
- Classification
- Clustering
- Pair classification
- Reranking
- Retrieval
- Semantic Textual Similarity (STS)
- Summarization
- Bitext mining

## How to Access

Official MTEB leaderboard available at: https://huggingface.co/spaces/mteb/leaderboard

Users can select different benchmarks:
- Multilingual leaderboard
- English-only leaderboard
- Domain-specific benchmarks

## Research Impact

MTEB has become the de facto standard for:
- Comparing embedding model performance
- Selecting appropriate models for specific tasks
- Tracking progress in text embedding research
- Validating new embedding approaches