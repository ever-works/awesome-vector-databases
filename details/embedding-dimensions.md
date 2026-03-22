## Overview

Embedding dimensions refer to the length of vector representations produced by embedding models. This is a crucial parameter affecting model capacity, storage requirements, and search performance.

## Common Dimension Sizes

### Text Embeddings
- **384**: Small models (all-MiniLM-L6-v2)
- **512**: Medium models (some GTE variants)
- **768**: BERT-base, many standard models
- **1024**: Larger models (BGE-large, multilingual-e5-large)
- **1536**: OpenAI text-embedding-ada-002, text-embedding-3-small
- **3072**: OpenAI text-embedding-3-large
- **8192**: Some specialized models

### Image Embeddings
- **512**: CLIP models (typical)
- **1024**: Larger vision models
- **2048**: High-capacity vision transformers

## Trade-offs

### Higher Dimensions
**Advantages:**
- More nuanced semantic representations
- Better task performance
- Higher capacity for complex concepts

**Disadvantages:**
- More storage (linear scaling)
- Slower distance computations
- Higher memory requirements
- Increased indexing time

### Lower Dimensions
**Advantages:**
- Faster search
- Less storage
- Lower memory footprint
- Faster index building

**Disadvantages:**
- Less expressive
- Potential information loss
- Lower task performance

## Matryoshka Embeddings

Modern approach allowing flexible dimensions:
- Single model supports multiple sizes
- Examples: 64, 128, 256, 512, 1024
- Important information in early dimensions
- Choose dimension at inference time
- Used by: OpenAI, Nomic, Alibaba GTE

## Storage Impact

### Example: 1M vectors
- 384-dim: ~1.5 GB (float32)
- 768-dim: ~3 GB
- 1536-dim: ~6 GB
- 3072-dim: ~12 GB

### With Quantization
- Binary (1-bit): 32x reduction
- int8: 4x reduction
- Enables larger dimension at same cost

## Choosing Dimensions

### For Your Application

**Small Dimensions (128-384):**
- Simple semantic matching
- Large-scale deployment
- Mobile/edge applications
- Cost-sensitive scenarios

**Medium Dimensions (512-1024):**
- General-purpose retrieval
- Balanced performance/cost
- Most production RAG systems

**Large Dimensions (1536+):**
- Complex semantic understanding
- Multi-lingual scenarios
- Specialized domains
- When accuracy is critical

## Dimensionality Reduction

Techniques to reduce dimensions:
- **PCA**: Principal Component Analysis
- **Random Projection**: Fast approximation
- **Matryoshka Training**: Learn multi-scale
- **Autoencoders**: Neural compression

## Model Examples by Dimension

**384-dim:**
- all-MiniLM-L6-v2
- paraphrase-MiniLM-L6-v2

**768-dim:**
- BERT-base models
- sentence-transformers defaults

**1024-dim:**
- BGE-large-en
- multilingual-e5-large
- GTE-large

**1536-dim:**
- OpenAI ada-002
- OpenAI text-embedding-3-small
- Cohere embed-v3

## Pricing

Concept; implementation costs vary by model and platform.