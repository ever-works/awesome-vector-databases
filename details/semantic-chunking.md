## Overview

Semantic chunking, sometimes called intelligent chunking, focuses on preserving the document's meaning and structure. Instead of using a fixed chunk size, it strategically divides the document at meaningful breakpoints—like paragraphs, sentences, or thematically linked sections.

## How It Works

Semantic chunking is an advanced technique that uses text embeddings to split documents based on their semantic content instead of arbitrary positions or formatting cues. Rather than slicing at fixed intervals, the algorithm looks for meaningful transitions in content and tries to preserve cohesive ideas within each chunk.

## Methods

### Percentile-Based Chunking

Splits occur when differences between sentences exceed a set percentile.

### Standard Deviation-Based Chunking

Chunks form when semantic differences go beyond a certain number of standard deviations, isolating major content shifts.

### Interquartile-Based Chunking

Splits text using the interquartile range, focusing on significant differences while ignoring minor variations.

## Advantages

Semantic chunking is one of the most accurate RAG chunking strategies for multi-topic documents:
- Related ideas remain grouped together
- Improves both recall quality and generation coherence
- Better context preservation
- Higher recall (91-92% vs 85-90% for recursive splitting)

## Trade-offs

Semantic chunking gives higher recall but costs more to run, as it requires embedding every sentence in your documents.

## Recommended Starting Points

Recursive character splitting at 400-512 tokens with 10-20% overlap works well for most text content and is the recommended starting point before investing in semantic chunking.

## Performance

Chroma's research showed:
- Recursive splitting: 85-90% recall at 400 tokens
- Semantic chunking: 91-92% recall
- The 2-3% improvement costs embedding every sentence

## Pricing

Implementation available in various RAG frameworks (LangChain, etc.)