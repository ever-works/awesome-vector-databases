## Overview

Scientific OCR specialized for equations and technical content.

## Features

- Multi-format output: LaTeX, MathML, AsciiMath, plain text, JSON
- Batch processing with parallelism
- Content detection: equations, tables, diagrams
- Confidence scoring per region
- PDF multi-page support
- CLI: scipix-cli ocr/serve/mcp

## Usage

```rust
// Rust integration via crate
cargo add ruvector-scipix
```

```javascript
import { SciPixClient } from '@ruvector/scipix';
const client = new SciPixClient({ baseUrl: 'http://localhost:8080' });
const result = await client.ocrFile('./equation.png', { formats: ['LaTeX'] });
```

```bash
scipix-cli ocr --input equation.png --format latex
```

## Pricing

Open-source, free.