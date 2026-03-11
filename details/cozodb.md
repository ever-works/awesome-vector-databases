## Overview

CozoDB is a unique database that combines relational, graph, and vector capabilities in a single system using Datalog as its query language. Starting from version 0.6, it includes vector search capabilities using HNSW indices.

## Features

- **Multi-Model**: Combines relational, graph, and vector data models
- **Datalog Queries**: Powerful declarative query language
- **Vector Search**: HNSW-based similarity search since v0.6
- **Embeddable**: Can run embedded in applications
- **Transactional**: Full ACID transaction support
- **Scalable**: Handles large datasets and high concurrency
- **Graph Analytics**: Native support for graph algorithms
- **Time Travel**: Built-in temporal queries

## Use Cases

- Knowledge graph applications with vector embeddings
- Complex graph analytics with semantic search
- Applications requiring combined relational and vector queries
- Embedded AI applications

## Query Language

Uses Datalog, a declarative logic programming language that's particularly powerful for graph queries and recursive operations.

## Integration

Can be embedded in Rust, Python, NodeJS, Java and C applications. Works well for AI applications requiring both structured and vector data.

## Pricing

Free and open-source under MPL-2.0 license.