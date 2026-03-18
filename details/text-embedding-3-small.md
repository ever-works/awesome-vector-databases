## Overview

text-embedding-3-small is OpenAI's improved, more performant version of the ada-002 embedding model, released January 25, 2024. It creates embeddings with 1536 dimensions optimized for latency and storage.

## Key Features

- **5x Price Reduction**: $0.00002 per 1k tokens (down from $0.0001 for ada-002)
- **Improved Performance**: Better accuracy on English and non-English tasks
- **Matryoshka Embeddings**: Support for shortened dimensions without losing quality
- **Dimension Flexibility**: Can adjust embedding size via dimensions API parameter

## Performance Improvements

Compared to text-embedding-ada-002:
- MIRACL average score: increased from 31.4% to 44.0%
- MTEB average score: increased from 61.0% to 62.3%

## Matryoshka Representation Learning

Unique feature allows shortening embeddings while maintaining performance. Store more important information in earlier dimensions, less important in later dimensions.

## Use Cases

- Cost-effective semantic search
- Large-scale embedding generation
- RAG applications on budget
- Applications requiring balance of performance and cost

## Technical Specifications

- **Default Dimensions**: 1536
- **Adjustable Range**: Can be shortened to smaller sizes
- **Context Window**: 8191 tokens
- **Output**: Normalized vectors

## Pricing

$0.00002 per 1,000 tokens (62% less expensive than text-embedding-3-large).