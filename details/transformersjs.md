## Overview

Transformers.js is a JavaScript library for running 🤗 Transformers directly in your browser with no server required. Designed to be functionally equivalent to the original Python library with a similar API.

## Key Features

- **No Server Required**: Run models entirely in the browser or Node.js
- **ONNX Runtime**: Uses ONNX Runtime for efficient model execution
- **Python API Parity**: Similar API to Python Transformers library
- **Multimodal Support**: Text, image, and audio tasks

## Capabilities

- **Text Embeddings**: Generate vector embeddings for semantic search
- **Zero-Shot Classification**: Classify text, images, and audio without training
- **Object Detection**: Detect objects in images
- **Text Generation**: Generate text with various models
- **Question Answering**: Extract answers from context

## Common Use Cases

**Vector Embeddings in Browser**: Popular model all-MiniLM-L6-v2 produces 384-dimension vectors from text, running entirely client-side

**Related Content**: Build semantic related posts or document similarity without backend infrastructure

**Privacy-Focused Applications**: All processing happens locally, ensuring user data privacy

## Installation

```javascript
import { pipeline } from "@huggingface/transformers";
```

## Example Applications

- Text embeddings in Bun, Deno, and Node.js
- Browser-based semantic search
- Client-side content recommendations
- Offline-capable AI features

## Platform Support

Works in:
- Modern browsers
- Node.js (ESM and CJS)
- Bun
- Deno

## Pricing

Free and open-source.