## Overview

AutoRAG is an automated framework that identifies optimal RAG modules for a given dataset, similar to AutoML practices in traditional machine learning. It automatically experiments with various RAG techniques to find the best pipeline configuration.

## Key Features

### Automated Optimization
- Automatically runs experiments to find the best RAG pipeline
- Creates all possible combinations of modules and parameters
- Executes pipelines with each configuration
- Selects optimal results according to predefined strategies
- Uses greedy algorithm for module selection

### Three Main Capabilities

1. **Data Creation**: Create RAG evaluation data from raw documents
2. **Optimization**: Automatically run experiments to find the best RAG pipeline
3. **Deployment**: Deploy the best pipeline with a single YAML file and Flask server support

## RAG Components Evaluated

AutoRAG examines strategies for:
- **Query Expansion**: Techniques to improve query quality
- **Retrieval**: Methods for finding relevant documents
- **Passage Augmentation**: Approaches to enhance retrieved content
- **Passage Reranking**: Strategies to reorder results
- **Prompt Creation**: Optimal prompt engineering techniques

## How It Works

### Optimization Process
1. Define evaluation data and metrics
2. Configure available modules and parameters for each stage
3. AutoRAG generates all possible combinations
4. Each configuration is tested automatically
5. Best performing pipeline selected based on metrics
6. Results and configurations saved for deployment

### Greedy Algorithm Approach
- Optimizes each node in the RAG pipeline sequentially
- Selects the most appropriate modules for each stage
- Balances performance metrics with computational efficiency
- Produces reproducible, optimized pipelines

## Evaluation & Results

All experimental results and data are publicly available through the GitHub repository, enabling:
- Reproducibility of optimization experiments
- Comparison across different datasets
- Understanding of module effectiveness
- Insights into RAG pipeline design

## Use Cases

- **RAG Pipeline Development**: Quickly find optimal configuration for new use cases
- **Performance Optimization**: Improve existing RAG systems systematically
- **Benchmarking**: Compare different RAG approaches objectively
- **Research**: Understand which techniques work best for specific domains
- **Production Deployment**: Deploy validated, optimized pipelines

## Research Background

Published in October 2024 on arXiv, the AutoRAG paper introduces systematic approaches to RAG optimization, bringing AutoML principles to the retrieval-augmented generation domain.

## Benefits

- Saves time on manual RAG tuning
- Removes guesswork from module selection
- Provides data-driven optimization
- Ensures reproducible results
- Simplifies deployment with YAML configuration

## Getting Started

1. Install AutoRAG from GitHub
2. Prepare evaluation dataset
3. Define optimization configuration
4. Run automated optimization
5. Deploy best pipeline

## Availability

Open-source framework available at: https://github.com/Marker-Inc-Korea/AutoRAG