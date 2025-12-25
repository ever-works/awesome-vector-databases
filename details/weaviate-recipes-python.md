---
title: Weaviate Recipes (Python)
slug: weaviate-recipes-python
brand: Weaviate
brand_logo: https://weaviate.io/_next/static/media/weaviate-logo-dark.5f2b6b9b.svg
source_url: https://github.com/weaviate/recipes/
category: Curated Resource Lists
tags: ["weaviate", "python", "jupyter-notebooks", "vector-database", "rag", "ai-integrations"]
featured: false
---

## Description

Weaviate Recipes (Python) is a GitHub repository of end-to-end Jupyter notebook examples demonstrating how to use Weaviate as a vector database from Python. The notebooks cover data ingestion, vector and hybrid search, generative AI workflows, RAG (Retrieval-Augmented Generation), and integrations with a wide range of tools and platforms.

## Features

### Repository Structure
- **Datasets**
  - Ready-to-use datasets for ingestion into a Weaviate cluster.
  - Supports examples of loading and indexing data for search and RAG scenarios.

- **Integrations**
  - Notebooks showing how to use Weaviate alongside other technologies and platforms.
  - Focus on combining Weaviate’s vector search with external compute, LLMs, data pipelines, and observability tools.

- **Weaviate Features**
  - Notebooks demonstrating Weaviate core capabilities, including:
    - Vector search
    - Hybrid search
    - Generative search
    - Reranking
    - Multi-tenancy
    - Use of `nearText`, `hybrid`, and `.generate` operators with multiple model providers

- **Weaviate Services**
  - Examples of how to build applications using Weaviate Services.
  - End-to-end workflows showing service-oriented usage patterns.

### Integrations Coverage
The repository aligns with Weaviate’s broader integrations ecosystem; example notebooks focus on connecting to tools from categories such as:

- **Cloud Hyperscalers**
  - Google Cloud
  - AWS
  - NVIDIA

- **Compute Infrastructure**
  - Modal
  - Replicate

- **LLM and Agent Frameworks**
  - Agno
  - CrewAI
  - Composio
  - DSPy
  - Dynamiq
  - LangChain
  - LlamaIndex
  - Pydantic
  - Semantic Kernel
  - Ollama
  - Haystack
  - Modaic

- **Data Platforms**
  - Databricks
  - Confluent
  - Box
  - Boomi
  - Spark
  - Unstructured
  - Firecrawl
  - Context Data
  - Aryn
  - Astronomer
  - Airbyte
  - IBM (Docling)
  - Cardinal
  - Contextual AI
  - Chonkie
  - Parallel

- **Operations / Monitoring / Evaluation**
  - AIMon
  - Arize
  - Cleanlab
  - Comet
  - DeepEval
  - Langtrace
  - LangWatch
  - Nomic
  - Patronus AI
  - Ragas
  - TruLens
  - Weights & Biases

These integrations are reflected in notebooks that show how to combine Weaviate with LLM frameworks, data ingestion pipelines, evaluation tools, and MLOps platforms.

### Weaviate Feature Examples
Some of the Weaviate functionality illustrated in the notebooks includes:
- Using **model providers** with Weaviate’s `nearText`, `hybrid`, and `.generate` operators.
- Applying **filters** to narrow search results (where-clause style queries, structured filtering alongside vector search).
- Implementing **vector search** for semantic retrieval.
- Implementing **hybrid search** that mixes keyword and vector-based retrieval.
- Using **generative search** to produce answers or summaries from retrieved context.
- Demonstrating **reranking** strategies to improve result ordering.
- Showcasing **multi-tenancy** patterns where applicable.

## Use Cases

- Learning how to connect a Python application to a Weaviate cluster.
- Building RAG pipelines that combine Weaviate with LLM and agent frameworks.
- Prototyping vector and hybrid search over your own or example datasets.
- Exploring integrations with cloud providers, data platforms, and evaluation tools.
- Using complete, runnable Jupyter notebooks as templates for production systems.

## Pricing

- The **Weaviate Recipes (Python)** repository itself is an open GitHub resource; no pricing information is specified in the provided content.
- Any costs would come from underlying platforms or services used in the examples (e.g., cloud providers, external model or data services), which are not detailed here.