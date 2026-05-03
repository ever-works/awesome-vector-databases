## Overview

Native embedding generation using ONNX Runtime in pure Rust. Supports multiple pretrained models and hardware acceleration.

## Features

- Pretrained models: all-MiniLM-L6-v2 (384 dim), BgeSmallEnV15 (384 dim), AllMpnetBaseV2 (768 dim)
- Pooling strategies
- GPU support: CUDA, TensorRT, CoreML, WebGPU
- Semantic similarity computation
- RuVector index integration for RAG

## Usage

```rust
use ruvector_onnx_embeddings::{Embedder, PretrainedModel};

#[tokio::main]
async fn main() -> anyhow::Result<()> {
    let mut embedder = Embedder::default_model().await?;
    let embedding = embedder.embed_one("Hello, world!")?; 
    let sim = embedder.similarity(
        "I love programming in Rust",
        "Rust is my favorite language"
    )?;
    println!("Similarity: {:.4}", sim);
    Ok(()) 
}
```

## Pricing

Open-source, free.