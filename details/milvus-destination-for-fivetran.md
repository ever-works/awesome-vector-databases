# Milvus Destination for Fivetran

**Category:** Data Integration & Migration  
**Brand:** Fivetran  
**Type:** Destination (Vector Database)

Milvus Destination for Fivetran lets you use Fivetran ELT pipelines to load data into Milvus or Zilliz Cloud as a vector database, supporting AI and similarity search workloads such as semantic search, RAG, and multi‑modal search.

---

## Overview

- Integrates Fivetran with **Milvus**, an open‑source vector database built for GenAI applications.
- Supports both **Milvus** and **Zilliz Cloud** (fully managed Milvus) as destinations.
- Designed to power AI use cases including **semantic search**, **Retrieval‑Augmented Generation (RAG)**, and **multi‑modal search** by syncing data into a vector database.
- Best‑practice recommendation is to run Milvus in **Zilliz Cloud** for quickest setup.

---

## Features

### Destination capabilities
- **Milvus and Zilliz Cloud support**  
  Fivetran can write to self‑managed Milvus or Zillan Cloud clusters as the destination.

- **GenAI and vector search workloads**  
  Data is loaded into Milvus as vectors suitable for high‑performance similarity search and AI applications (semantic search, RAG, multi‑modal use cases).

### Source connector support
Only the following Fivetran connectors are supported as sources for this destination:
- **Snowflake** (database connector)
- **BigQuery** (database connector)
- **Databricks** (database connector)

The documentation also references guidance on how to **sync data from sources not directly supported** by the Milvus destination, implying workflows or intermediate steps for unsupported sources.

### Deployment model
- **SaaS deployment supported**  
  Milvus destination is supported when using Fivetran’s **SaaS Deployment** model.

### Setup and configuration
- **Step‑by‑step setup guide**  
  A dedicated Milvus setup guide walks through connecting a Milvus vector database (or Zilliz Cloud cluster) as a Fivetran destination.

- **Partner‑built destination**  
  The Milvus destination is identified as **partner‑built**, with documentation and implementation maintained by the Milvus/Zilliz team.

### Data type mapping
Fivetran’s standard data types are mapped to Milvus data types as follows:

| Fivetran Data Type | Milvus Destination Data Type |
| -------------------| -----------------------------|
| BOOLEAN            | BOOLEAN                      |
| SHORT              | INT16                        |
| INT                | INT32                        |
| LONG               | INT64                        |
| FLOAT              | FLOAT                        |
| DOUBLE             | DOUBLE                       |
| DECIMAL            | VARCHAR                      |
| LOCALDATE          | VARCHAR                      |

These mappings define how source schema fields are stored in Milvus when synced via Fivetran.

---

## Integrations

- **Vector Database:** Milvus, Zilliz Cloud  
- **Supported Source Databases:**
  - Snowflake
  - BigQuery
  - Databricks

---

## Pricing

- The provided documentation content does **not** specify any dedicated pricing details or plans specific to the Milvus destination.
- Fivetran generally operates on **usage‑based pricing**, described separately in Fivetran’s “Usage‑Based Pricing” documentation, but no Milvus‑specific pricing tiers or constraints are mentioned in the extracted content.