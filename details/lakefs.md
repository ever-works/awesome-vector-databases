## Overview

lakeFS is a data version control platform that provides a Git-like experience for managing data in object storage. In the context of AI and vector workloads, it enables teams to version embeddings, index manifests, and encoder configurations as immutable commits, ensuring reproducibility and governance.

## Key Capabilities for Vector Workflows

- **Version embeddings, index manifests, and encoder configs** as immutable commits for full traceability
- **Rebuild on isolated branches** when models, parameters, or datasets change without impacting production
- **Validate recall and latency in CI/CD** before promoting a new index version
- **Instant rollback** by serving a previous commit or tagged version
- **Zero-copy branching** to mitigate additional storage costs for embeddings and index artifacts
- **Retention and GC policies** for untagged builds to manage storage efficiently

## Recommended Integration Pattern

- Use Spark or Ray to generate embeddings
- Use dbt for upstream feature engineering
- Use Airflow or Dagster to orchestrate the branch → build → benchmark → tag → merge cycle
- Exporters publish index files (HNSW/IVF/PQ/ScaNN) or backend apply manifests with a resolver mapping {commit → vector backend URI} for backends like Milvus, pgvector, Weaviate, or Pinecone

## Engineering Tradeoffs

**Pros:**
- Reproducibility across environments
- Backend flexibility — works with any vector database
- One-click rollback via versioned commits
- Automation-controlled promotion gates

**Cons:**
- Additional storage overhead for embeddings and index artifacts (mitigated by zero-copy branching and GC policies)

## Pricing

lakeFS offers a free open-source edition and a managed cloud offering with enterprise features.