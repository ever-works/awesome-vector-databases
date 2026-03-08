## Overview

ColBERT introduces a late interaction architecture that independently encodes the query and the document using BERT and then employs a cheap yet powerful interaction step that models their fine-grained similarity.

## Late Interaction Architecture

Late interaction operates at the token level:
- Uses one vector for each token
- Represents both documents and queries as bags of tokens
- Document relevance computed via maxsim operator
- Compares every query token to every document token

## Key Advantages

- Strong generalization and robustness, particularly in out-of-domain settings
- Fine-grained, token-level representations
- Well-suited for novel use cases: reasoning-based or cross-modality retrieval
- More expressive than single-vector methods

## Evolution

- **ColBERT** (SIGIR'20): Original late interaction approach
- **ColBERTv2** (TACL'21): Effective and efficient retrieval via lightweight late interaction
- **PLAID indexing**: De facto standard indexing method for multi-vector retrieval

## Challenges

The multi-vector approach requires storing significantly more data than single-vector methods, posing challenges for:
- Storage efficiency
- Index size
- Retrieval speed at scale

## Research Impact

Pioneered modern multi-vector retrieval methods. A First Workshop on Late Interaction and Multi Vector Retrieval is scheduled for ECIR 2026, demonstrating the growing importance of this approach.

## Availability

Open-source on GitHub with active research community.