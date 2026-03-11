## Overview

MaxSim (Maximum Similarity) is ColBERT's late interaction similarity function that enables precise, token-level matching between queries and documents. It's particularly effective for long-document datasets.

## How MaxSim Works

1. Calculate cosine similarity between every query token embedding and all document token embeddings
2. Keep track of each query token embedding's maximum score
3. Sum these maximum scores to get the total query-document score

## Performance on Long Documents

On long-document datasets, the context-level MaxSim is by a large margin the most effective scoring function, with cross-context MaxSim as a solid second place.

## Comparison with Traditional Methods

Traditional dense retrieval compresses entire documents into single vectors, losing fine-grained information. MaxSim preserves token-level interactions while remaining computationally efficient.

## Use Cases

- Long-document retrieval
- Legal document search
- Scientific paper matching
- Code search
- Technical documentation retrieval

## Implementation in RAG

MaxSim is used as a re-ranking stage after initial retrieval:
1. Initial retrieval with BM25 and/or dense vectors
2. Candidate fusion via RRF
3. MaxSim re-ranking over top-k candidates

## Performance Benefits

Late interaction ranking models deliver high-quality ranking results on large-scale datasets, which is crucial for RAG systems.

## Platform Support

Vespa announced Long-Context ColBERT support with MaxSim in 2026, enabling efficient ColBERT search at scale.