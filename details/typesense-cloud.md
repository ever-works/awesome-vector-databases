# Typesense Cloud

**Website:** https://cloud.typesense.org  
**Category:** Curated Resource Lists / Managed Search-as-a-Service  
**Tags:** managed-service, vector-search, hybrid-search

## Overview
Typesense Cloud is the fully managed, hosted SaaS version of the open‑source Typesense search engine. It provides globally distributed, low‑latency search infrastructure, including support for vector and hybrid search workloads, without requiring users to manage servers or clusters themselves.

## Features

### Managed Search Infrastructure
- Fully managed hosting of the Typesense open-source search engine
- Dedicated clusters (no shared multi-tenant usage limits by record or operation)
- Multi-node high availability configuration available
- Optional capacity auto-scaling based on data and traffic
- NVMe SSD storage for fast I/O on large documents
- Configurable cluster sizes up to:
  - 1 TB RAM
  - 960 vCPUs

### Performance & Global Distribution
- Search Delivery Network (SDN) – CDN-like global distribution specifically for search
- Replication of search indices across multiple geographic regions
- Latency-based routing of search traffic to the closest node
- Designed to handle high traffic volumes (serves 10B+ searches per month across many clusters)

### Regions / Data Centers
Search Delivery Network available in 26 regions, including:
- North America: N. California, Oregon, N. Virginia, Ohio, Canada
- South America: São Paulo
- Europe: Ireland, London, Paris, Zurich, Frankfurt, Stockholm, Milan, Spain
- Africa & Middle East: Cape Town, Bahrain, UAE
- Asia: Mumbai, Hyderabad, Singapore, Jakarta, Seoul, Osaka, Tokyo
- Oceania: Melbourne, Sydney

### Search Capabilities
- Supports traditional, vector, and hybrid search use cases (via underlying Typesense engine)
- Designed for low-latency, high-relevance search experiences across global user bases

### Compute & Acceleration
- High-CPU configurations for heavy search traffic
- GPU acceleration option for efficient embedding generation

### Operations & Configuration
- Clusters can be spun up and down on demand for benchmarking and tuning
- Cloud dashboard for configuration and tailoring of the search experience (e.g., index and search settings)

## Pricing
- **Hourly Pricing**
  - Pay by the hour for clusters
  - Spin clusters up and down as needed
  - Suitable for benchmarking, right-sizing, and dynamic workloads
- **No Per-Search or Per-Record Charges**
  - No additional fees based on number of records or search operations
  - Usage limited only by the capacity of the dedicated cluster
- Detailed pricing and calculators are available on their pricing page (via `/pricing/calculator`).