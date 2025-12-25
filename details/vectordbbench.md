---
title: VectorDBBench
slug: vectordbbench
url: https://github.com/zilliztech/VectorDBBench
category: benchmarks-evaluation
brand: zilliz
brand_logo: https://avatars.githubusercontent.com/u/67472536?s=200&v=4
source_url: https://github.com/zilliztech/VectorDBBench
images:
  - https://opengraph.githubassets.com/1/zilliztech/VectorDBBench
tags:
  - benchmark
  - evaluation
  - vector-databases
license: MIT
featured: false
---

## Overview

VectorDBBench is an open‑source benchmarking toolkit for vector databases. It provides implementation code, configuration, and scripts to run standardized benchmarks across multiple vector database systems locally or in CI environments.

## Features

- **Standardized benchmarking framework** for evaluating vector databases under a common setup.
- **Multi‑database support** through pluggable implementations in the `vectordb_bench` module.
- **Configurable benchmark runs** via configuration files and environment variables (example in `.env.example`).
- **Containerized environment** using the provided `Dockerfile` and `.devcontainer` setup for reproducible runs.
- **CI integration** enabled by GitHub workflow definitions in `.github/workflows`.
- **Automated tests** in the `tests` directory to validate benchmark logic and integrations.
- **Scripted installation and setup** with resources under the `install` directory and `Makefile` targets.
- **Open‑source, extensible design** under the MIT license, allowing customization and contribution.

## Pricing

VectorDBBench is open source and available free of charge under the MIT license.