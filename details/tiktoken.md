## Overview

tiktoken is OpenAI's tokenizer library that enables fast token counting and text encoding/decoding using the same tokenizers used by OpenAI's language models. It is commonly used in chunking strategies for vector databases to ensure accurate token counts before embedding.

## Features

- Fast token encoding and decoding for multiple tokenizer models (cl100k_base, r50k_base, p50k_base)
- Compatible with GPT-4, GPT-3.5-Turbo, and other OpenAI models
- Supports encoding, decoding, and token counting in a single pass
- Written in Rust with Python bindings for performance
- Useful for calculating chunk sizes when preparing documents for vector database ingestion

## Common Use Cases

- Estimating token counts before sending text to embedding models
- Implementing fixed token window chunking strategies
- Calculating overlap between chunks for semantic coherence
- Validating that text inputs fit within model context limits

## Pricing

Free and open-source under the MIT license.