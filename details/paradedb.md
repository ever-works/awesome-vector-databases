## Overview

ParadeDB pg_search is a Postgres extension that enables fast full-text, faceted and hybrid search over Postgres tables using the BM25 algorithm. It is built on top of Tantivy, the Rust-based alternative to Apache Lucene, using pgrx.

## BM25 Implementation

ParadeDB uses Rust to implement BM25 indexes, adding them to PostgreSQL through the open-source pg_search extension. BM25 (short for Best Matching 25, often called Okapi BM25) measures relevance by balancing term frequency, document rarity, and length normalization.

While PostgreSQL supports basic term matching, it lacks a native implementation of BM25, the probabilistic ranking function that underpins most modern search systems including Elasticsearch.

## Hybrid Search

Hybrid search in PostgreSQL combines BM25's lexical precision with vector embeddings' semantic understanding using RRF (Reciprocal Rank Fusion) fusion.

### How It Works
- ParadeDB brings production-ready full text search with BM25 scoring for lexical relevance
- pgvector delivers vector similarity for semantic understanding
- Hybrid search combines BM25 scores with pgvector embeddings to enhance search experiences
- Combines the precision of BM25 with the semantic understanding of vector search

## Key Benefits

### No External Dependencies
ParadeDB and pgvector make hybrid search possible without external dependencies—everything runs in your existing database with ACID guarantees and transactional consistency.

### Production-Ready
- Built on proven technology (Tantivy)
- Full ACID compliance
- Transactional consistency
- Integrates seamlessly with existing PostgreSQL deployments

## Use Cases

- Applications requiring both keyword and semantic search
- E-commerce product search
- Document retrieval systems
- Knowledge bases requiring precise and semantic matching
- RAG applications needing hybrid retrieval

## Availability

Open-source on GitHub and available through PGXN (PostgreSQL Extension Network).

## Pricing

Free and open-source.