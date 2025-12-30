# Neighbor

**Category:** SDKs & Libraries  
**Website:** https://github.com/ankane/neighbor  
**Ecosystem:** Ruby, Rails

## Overview
Neighbor is a Ruby gem that adds approximate nearest neighbor (ANN) and vector similarity search to Rails applications. It integrates with multiple database backends, including pgvector, to enable efficient vector-based querying directly from Ruby.

## Features
- **Nearest neighbor search for Rails**  
  - Provides high-level Ruby/Rails interfaces for performing nearest neighbor and similarity searches.

- **Database backend support**
  - **Postgres**
    - Supports the `cube` extension.
    - Supports the `pgvector` extension for vector similarity search.
  - **MariaDB 11.8**
    - Native support for nearest neighbor search on this version.
  - **MySQL 9 (experimental)**
    - Nearest neighbor searching supported when using HeatWave (experimental status).
  - **SQLite (experimental)**
    - Supports vector search via `sqlite-vec`.

- **Additional ecosystem integrations**
  - Companion libraries for other storage backends:
    - **Redis** via `neighbor-redis`.
    - **S3-based vectors** via `neighbor-s3`.

- **Ruby gem packaging**
  - Distributed as a standard Ruby gem for easy inclusion in Rails and other Ruby applications.

- **Open-source licensing**
  - Licensed under the MIT license.

## Pricing
Neighbor is open source under the MIT license and can be used free of charge.