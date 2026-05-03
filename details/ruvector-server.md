## Overview

Server exposing RuVector via HTTP and gRPC.

## Features

- REST API for search/insert
- gRPC support

## Usage

```bash
cargo install ruvector-server
ruvector-server --port 8080 --data ./vectors

# REST API
curl -X POST http://localhost:8080/search -d '{"vector": [0.1, 0.2], "limit": 10}'
```

## Pricing

Open-source, free.