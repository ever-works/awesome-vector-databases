## Overview

SLIM (Sparsified Late Interaction for Multi-vector retrieval with inverted indexes) addresses efficiency challenges in multi-vector retrieval systems like ColBERT while maintaining competitive accuracy.

## Problem Statement

ColBERT is the most established multi-vector retrieval method based on late interaction of contextualized token embeddings. However:
- Efficient ColBERT implementations require complex engineering
- Cannot take advantage of off-the-shelf search libraries
- High storage and computational requirements

## SLIM Solution

SLIM maps each contextualized token vector to a sparse, high-dimensional lexical space before performing late interaction between these sparse token embeddings.

## Architecture

### Two-Stage Retrieval
1. **Inverted index retrieval**: Initial candidate retrieval using sparse representations
2. **Score refinement module**: Approximates sparsified late interaction

### Library Compatibility
Fully compatible with off-the-shelf lexical search libraries such as Lucene, enabling easier deployment and maintenance.

## Performance Results

Experiments on MS MARCO Passages show:
- Similar ranking accuracy compared to ColBERT-v2
- **40% less storage** required
- **83% decrease in latency**
- Competitive accuracy on MS MARCO Passages and BEIR benchmarks
- Much faster on CPUs compared to ColBERT

## Availability

- Published at SIGIR 2023
- Source code and data integrated into Pyserini IR toolkit
- Available on arXiv (2302.06587)
- GitHub: alexlimh/SLIM

## Comparison with ColBERT

**SLIM Advantages**:
- Lower storage requirements
- Faster retrieval
- Compatible with existing search infrastructure
- Simpler deployment

**ColBERT Advantages**:
- Slightly higher accuracy in some scenarios
- Established ecosystem

## Applications

- Large-scale passage retrieval
- Question answering systems
- Document search
- Any scenario requiring multi-vector retrieval with efficiency constraints