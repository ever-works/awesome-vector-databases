## Overview

LanceDB is an embedded columnar database built on Apache Arrow's Lance format, optimized for multimodal vectors (images, text, video).

## Features

- Zero-copy reads leveraging Arrow
- SQL queries for hybrid vector + full-text search
- Cloud sync with LanceDB Cloud
- IVF-PQ indexing and versioning
- Python/Rust bindings, zero dependencies

## Use Cases

- Computer vision search
- Large-scale multimodal analytics
- Edge AI and prototyping

## Comparisons

| Feature          | LanceDB vs Chroma          | LanceDB vs Faiss     |
|------------------|----------------------------|----------------------|
| Storage         | Columnar, multimodal      | Full DB w/ persistence |
| Queries         | SQL                       | Index-only           |
| Deployment      | Embedded, zero-copy       | Library              |

## Pricing

Open-source under Apache 2.0 license.