## Overview

Victor is a web-optimized vector database implemented in Rust and compiled to WebAssembly.

## Features

- Rust API (using native filesystem or transient in-memory filesystem)
- Web API (using Private Origin File System)
- Very efficient vector storage format (1.5 KB for 1536 dimensions vs. 20.6 KB JSON)
- PCA for vector compression when storage space is low

## JavaScript Usage

### Installation

```
npm install victor-db
```

### Example

```javascript
import { Db } from "victor";

const db = await Db.new();

const content = "My content!";
const tags = ["these", "are", "tags"];
const embedding = new Float64Array(/* your embedding here */);

// write to victor
await db.insert(content, embedding, tags);

// read the 10 closest results from victor that are tagged with "tags"
const result = await db.search(embedding, ["tags"], 10);
assert(result[0].content == content);

// clear database
await db.clear();
```

See `www/` for complete examples including OpenAI embeddings.

## Rust Usage

### Installation

```
cargo add victor-db
```

### Example

```rust
use std::path::PathBuf;

use victor_db::native::Db;

let _ = std::fs::create_dir("./victor_test_data");
let mut victor = Db::new(PathBuf::from("./victor_test_data"));

victor.clear_db().await.unwrap();

victor
    .add(
        vec!["Pineapple", "Rocks"], // documents
        vec!["Pizza Toppings"],     // tags (only used for filtering)
    )
    .await;

victor
    .add_single("Cheese pizza", vec!["Pizza Flavors"])
    .await;

let nearest = victor
    .search("Hawaiian pizza", vec!["Pizza Toppings"], 10)
    .await
    .first()
    .unwrap()
    .content
    .clone();
assert_eq!(nearest, "Pineapple".to_string());
```

## Pricing

Free and open-source.