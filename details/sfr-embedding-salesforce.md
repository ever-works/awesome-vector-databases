## Overview

SFR-Embedding is Salesforce AI Research's groundbreaking family of embedding models that have achieved state-of-the-art performance on major benchmarks. The family includes models for both general text and code retrieval.

## SFR-Embedding-Mistral (Text Embeddings)

### Performance

**MTEB Benchmark Leadership**:
- Average score: **67.6 across 56 datasets**
- #1 position on MTEB leaderboard (as of Feb 2024)
- Surpasses 150+ embedding models including proprietary models from:
  - OpenAI (text-embedding-3-large)
  - Cohere (embed-english-v3.0)
  - Voyage AI (voyage-lite-02-instruct)

### Improvements Over Base Model

Built upon E5-mistral-7b-instruct and Mistral-7B-v0.1, with significant enhancements:
- **Retrieval tasks**: Score improved from 56.9 to **59.0** (+2.1)
- **Clustering tasks**: **+1.4 improvement** over E5-mistral-7b-instruct

### Optimal Use Case

Excels in retrieval tasks, making it ideal for Retrieval Augmented Generation (RAG) workflows where finding and selecting relevant information from large datasets is crucial.

## SFR-Embedding-2_R

An advanced version with multi-stage training that further improves on the original SFR-Embedding-Mistral.

## SFR-Embedding-Code (Code Embeddings)

### Revolutionary Code Retrieval

Redefines state-of-the-art in code retrieval:
- **Outperforms 2nd best model by over 20%** on CoIR benchmark
- #1 ranking on CoIR (Code Information Retrieval) benchmark
- Designed for both code and text retrieval

### Model Sizes

Available in three sizes to balance performance and efficiency:

**SFR-Embedding-Code-2B_R**: 2 billion parameters
- Highest quality
- #1 on CoIR benchmark

**SFR-Embedding-Code-400M_R**: 400 million parameters
- Best-performing model under 0.5B parameters
- Excellent balance of speed and quality

**SFR-Embedding-Code-7B**: 7 billion parameters (if available)
- Maximum quality for critical applications

### Language Support

Supports **12 programming languages** including:
- Python
- Java
- C++
- JavaScript
- C#
- And 7 more

### Versatility

Unlike code-only models, SFR-Embedding-Code handles both:
- Code-to-code similarity
- Natural language queries to code search
- Code documentation retrieval
- Cross-language code search

## Use Cases

### Text Embeddings
- RAG pipelines requiring high retrieval accuracy
- Semantic search engines
- Document clustering and classification
- Question answering systems

### Code Embeddings
- Code search engines
- Developer tools and IDEs
- Documentation retrieval
- Code recommendation systems
- Duplicate code detection
- Cross-language code migration assistance

## Technical Foundation

SFR-Embedding leverages transfer learning and advanced training techniques to push beyond previous state-of-the-art models, demonstrating that careful training methodology can achieve significant improvements.

## Availability

**Hugging Face Models**:
- Salesforce/SFR-Embedding-Mistral
- Salesforce/SFR-Embedding-2_R
- Salesforce/SFR-Embedding-Code-400M_R
- Salesforce/SFR-Embedding-Code-2B_R

**License**: Released for research purposes

**Collection**: All models available in the SFR-Embedding collection on Hugging Face

## Impact

SFR-Embedding represents a significant milestone in embedding model development, proving that focused research can achieve meaningful improvements over existing state-of-the-art models from well-funded labs.