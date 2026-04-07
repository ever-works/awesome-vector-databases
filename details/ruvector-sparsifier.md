## Overview

Maintains a small graph behaving like the large one for efficient queries.

## Components

| Component | What it does |
|-|-|
| Backbone | Spanning forest guaranteeing connectivity |
| Importance scorer | Random walks for edge importance |
| Spectral sampler | Proportional edge keeping, reweighting |
| Auditor | Verifies approximation quality |

49 tests, benchmarks, WASM bindings.

## Installation

```sh
cargo add ruvector-sparsifier
```

## Pricing

Free and open-source.