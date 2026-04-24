# RediSearch

**RediSearch** is a Redis module that provides advanced querying, secondary indexing, full-text search, and vector similarity search capabilities for data stored in Redis.

[Source code on GitHub](https://github.com/RediSearch/RediSearch)

## Features

- **Full-text indexing** of multiple fields in Redis hashes
- **Incremental indexing** without performance loss
- **Document ranking** using tf-idf, with optional user-provided weights
- **Field weighting** for search relevance
- **Complex boolean queries** with AND, OR, and NOT operators
- **Prefix matching, fuzzy matching, and exact-phrase queries
- **Double-metaphone phonetic matching
- **Auto-complete suggestions** with fuzzy prefix suggestions
- **Stemming-based query expansion** in multiple languages (using Snowball)
- **Chinese-language tokenization and querying** (using Friso)
- **Numeric filters and ranges
- **Geospatial searches** using Redis geospatial indexing
- **Powerful aggregations engine** for data analysis
- **Support for all UTF-8 encoded text
- **Flexible document retrieval**: full documents, selected fields, or just document IDs
- **Sorting of results** (e.g., by creation date)
- **Geoshape indexing
- **Vector similarity search:**
  - KNN (k-nearest neighbors)
  - Filtered KNN
  - Range query for vector data
- **Cluster support:**
  - Distributed cluster mode for scaling to billions of documents across many servers (available in Redis Cloud and Redis Enterprise Software)

## License

- Redis Source Available License 2.0 (RSALv2) or Server Side Public License v1 (SSPLv1)

## Pricing

- RediSearch is open source. Distributed cluster features are available as part of Redis Cloud and Redis Enterprise Software (pricing details for those are not provided here).