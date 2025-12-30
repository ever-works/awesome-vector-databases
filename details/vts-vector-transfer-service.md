# VTS (Vector Transfer Service)

VTS is an open-source tool for transforming and transporting vectors and unstructured data, focused on data migration and connectivity for Milvus and external systems.

![VTS Architecture](https://raw.githubusercontent.com/zilliztech/vts/main/docs/images/vts-architecture.png)

---

## Overview

- **Type:** Open-source data migration and connector service
- **Primary focus:** Moving and synchronizing vector and unstructured data between Milvus instances and other systems
- **Ecosystem:** Built and maintained by Zilliz
- **License:** Apache-2.0

---

## Features

Based on the available repository information and description, VTS provides:

### Core Capabilities
- Transformation and transportation of **vector data**
- Handling of **unstructured data**
- Data **migration** between different Milvus instances
- **Connector** capabilities to integrate Milvus with external systems

### Integration & Connectors
- Designed as a **data connector layer** around Milvus
- Plugin-oriented structure (via `plugins` directory) enabling:
  - Source and sink plugins for different systems (exact list defined in code/plugins)
  - Extensible connectors for additional data sources/targets

### Workflow & Orchestration
- Uses a **SeaTunnel-based** architecture (`seatunnel-api`, `seatunnel-common`, `seatunnel-ci-tools`), implying:
  - Pipeline-style configuration for data movement
  - Transformation stages between sources and sinks

### Deployment & Operations
- **Containerized deployment** support (via `ci/docker` directory)
- **Kubernetes deployment manifests** (under `deploy/kubernetes/seatunnel`), enabling:
  - Clustered or cloud-native deployment
  - Integration into existing Kubernetes environments
- Configuration-driven behavior (via `config` directory) for:
  - Defining data sources and targets
  - Tuning pipeline behavior and runtime parameters

### Documentation & Tooling
- Documentation assets (under `docs`) including architecture diagrams and usage guidance
- Build and runtime utilities (under `bin`) to help run and manage VTS components

> Note: For a complete, up-to-date list of specific source/sink plugins and transformations, refer to the `plugins` and `docs` directories in the repository.

---

## Pricing

- VTS is an **open-source project** released under the **Apache-2.0 license**.
- No paid pricing plans are listed in the provided content.

---

## Links

- **Source Code & Docs:** https://github.com/zilliztech/vts
- **Project Homepage (vendor):** https://zilliz.com/ (for broader Milvus ecosystem context)