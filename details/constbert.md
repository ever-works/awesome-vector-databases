## Overview

ConstBERT is a novel approach to reduce the storage footprint of multi-vector retrieval by encoding each document with a fixed, smaller set of learned embeddings. ConstBERT compresses token-level BERT embeddings into a fixed number (C) of document-level vectors using a learned linear projection.

## Problem Addressed

Multi-vector retrieval methods, exemplified by the ColBERT architecture, have shown substantial promise for retrieval. However, they come at a high cost in terms of storage since a (potentially compressed) vector needs to be stored for every token in the input collection.

## Key Benefits

### Storage Efficiency
Unlike ColBERT, which scales linearly with the number of token embeddings per document, ConstBERT maintains a consistent index size by using a fixed number of embeddings. This efficiency extends across the BEIR datasets, with ConstBERT consistently reducing index sizes by over 50% compared to ColBERT at equivalent effectiveness.

### Better Memory Management
Document representations become of a fixed size on disk, allowing for better OS paging management.

### Computational Efficiency
Instead of iterating over dozens or hundreds of vectors per document, ConstBERT enables efficient late interaction scoring across a compact set of learned vectors. This results in lower query latency and better computational efficiency.

## Performance

Through experiments using the MSMARCO passage corpus and BEIR with the ColBERT-v2 architecture, the research finds that passages can be effectively encoded into a fixed number of vectors while retaining most of the original effectiveness.

## Availability

Code: https://github.com/pisa-engine/ConstBERT
Presented at ECIR 2025 (European Conference on Information Retrieval)
Published: April 2025

## Pricing

Free and open-source research implementation.