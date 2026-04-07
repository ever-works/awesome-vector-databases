## Overview

Native bindings for RuVector vector database in Node.js using napi-rs.

## Features

- Full RuVector API access in Node.js
- High performance via native Rust

## Usage

```javascript
const { RuVector } = require('@ruvector/node');
const db = new RuVector({ dimensions: 1536 });
db.insert('doc1', embedding, { title: 'Hello' });
const results = db.search(queryEmbedding, 10);
```

## Pricing

Open-source, free.