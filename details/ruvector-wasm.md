## Overview

WebAssembly bindings for RuVector, suitable for browsers and serverless edge.

## Features

- Vector insert and search in WASM
- Lightweight for client-side use

## Usage

```javascript
import { RuVectorWasm } from '@ruvector/wasm';
const db = await RuVectorWasm.create({ dimensions: 384 });
await db.insert('doc1', embedding);
const results = await db.search(query, 5);
```

## Pricing

Open-source, free.