## Features

- Extremely lightweight: Implemented as an Axum server with around 600 lines of code, easy to customize.
- High performance: Comparable speed to advanced vector databases on small to medium datasets, with slightly better accuracy.
- Vertical scaling: All indexes stored in memory, scales to 100 million+ vector dimensions.
- Open-source: MIT licensed.

## Upcoming Features

- Powerful queries with metadata filtering without slowing search.
- Integrated embedding models (SBert, Hugging Face, OpenAI, Cohere).
- TypeScript/Python client libraries via OpenAPI schema.

## Getting Started

### Docker
```
docker run -p 8000:8000 ghcr.io/m1guelpf/tinyvector:edge
```
Bind volume to `/tinyvector/storage` for persistence in Docker Compose/Kubernetes.

### From Source
Install via `cargo install tinyvector` or build from repo with `cargo build --release`.

## Use Cases

- Chat with documents using embeddings.
- Website or store search (under 1M items).

## License

MIT License.