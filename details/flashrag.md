## Overview

FlashRAG is a Python toolkit for the reproduction and development of Retrieval Augmented Generation (RAG) research. FlashRAG is an efficient and modular open-source toolkit designed to assist researchers in reproducing and comparing existing RAG methods and developing their own algorithms within a unified framework.

## Benchmarks and Algorithms

The toolkit includes:
- 36 pre-processed benchmark RAG datasets
- 23 state-of-the-art RAG algorithms, including 7 reasoning-based methods
- Support for reasoning-based methods that combine reasoning ability with retrieval (Search-o1, R1-Searcher, ReSearch)

## Key Features

### Multimodal RAG Support

Multimodal RAG support has been added, including MLLMs like Llava, Qwen, InternVL, and various multimodal retrievers with Clip architecture.

### Reasoning Pipeline

A new paradigm that combines reasoning ability and retrieval, representing a significant advancement in RAG systems for complex reasoning tasks.

### RAG Method Categories

RAG methods are categorized into four types based on their inference paths:
- **Sequential**: Sequential execution of RAG process
- **Conditional**: Implements different paths for different types of input queries
- **Branching**: Executes multiple paths in parallel, merging responses
- **Loop**: Iteratively performs retrieval and generation

## Publication

The technical paper "FlashRAG: A Python Toolkit for Efficient RAG Research" was accepted to the Resource Track of the 2025 ACM Web Conference (WWW 2025).

## Pricing

Free and open-source.