---
title: Vertex AI Pipelines
slug: vertex-ai-pipelines
brand: Google Cloud
brand_logo: https://cloud.google.com/images/social-icon-google-cloud-1200-630.png
category: curated-resource-lists
source_url: https://cloud.google.com/vertex-ai/docs/pipelines/introduction
featured: false
images:
  - https://cloud.google.com/static/vertex-ai/images/vertex-ai-pipelines-diagram.svg
---

## Overview

Vertex AI Pipelines is a serverless machine learning orchestration service on Google Cloud for building, automating, and managing ML pipelines. It supports MLOps workflows such as training, evaluation, deployment, and continuous retraining, and can be used to generate embeddings and manage vector search indexes for search and recommendation systems.

## Features

- **Serverless pipeline orchestration**  
  - Automates end-to-end ML workflows without managing infrastructure.  
  - Supports batch execution of ML pipelines.

- **Framework support**  
  - Run pipelines defined with **Kubeflow Pipelines (KFP)**.  
  - Run pipelines defined with **TensorFlow Extended (TFX)**.  
  - Guidance on choosing a framework via "Interfaces to define a pipeline".

- **MLOps workflow automation**  
  - Encodes ML workflows as pipelines for training, evaluation, and deployment.  
  - Enables continuous retraining on new production data.  
  - Supports applying MLOps strategies (automation, monitoring, governance) on Vertex AI.

- **Pipeline structure and execution model**  
  - Pipelines are modeled as **directed acyclic graphs (DAGs)** of tasks.  
  - Each task is a containerized step in the workflow.  
  - Tasks can be developed:  
    - As **Python-based components**.  
    - As **prebuilt container images**.  
  - Pipelines are defined using SDKs and compiled to **YAML** as an intermediate representation.  
  - Tasks run **in parallel by default**, with the option to link tasks for **sequential execution** via input/output dependencies.

- **Pipeline tasks and components**  
  - Each pipeline task performs a specific step such as data processing, training, evaluation, or deployment.  
  - Components can be reused across multiple pipelines.  
  - Input-output dependencies connect tasks and determine data flow.

- **Lifecycle management**  
  - Supports the full lifecycle of an ML pipeline: definition, compilation, execution, and reuse.  
  - Pipelines can be rerun with new parameters or data for experimentation or retraining.

- **Metadata tracking and lineage**  
  - Integrates with **Vertex ML Metadata** to track lineage of ML artifacts.  
  - Captures relationships between datasets, models, pipeline runs, and other artifacts for auditability and reproducibility.

- **Experiment tracking**  
  - Pipeline runs can be added to **experiments** for organizing and comparing different runs.  
  - Facilitates tracking changes in configurations, data, and results across experiments.

- **Ecosystem integration and examples**  
  - Example notebooks available via:  
    - Google Colab  
    - Colab Enterprise  
    - Vertex AI Workbench  
    - GitHub sample repository  
  - Sample notebook: *"Vertex AI Pipelines: Lightweight Python function-based components, and component I/O"*.

- **Vector search workflows (from item description)**  
  - Supports pipelines that **generate embeddings** for unstructured data.  
  - Can **create or update vector search indexes** as part of the pipeline.  
  - Suitable for MLOps workflows backing **vector database–based search and recommendation systems**.

## Pricing

The provided content does not include pricing information or plan details for Vertex AI Pipelines. For current pricing, refer to the official Google Cloud Vertex AI pricing documentation.