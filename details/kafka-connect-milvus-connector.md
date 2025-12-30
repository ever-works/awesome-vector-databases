# Kafka Connect Milvus Connector

**Category:** Data Integration & Migration  
**Brand:** Zilliz  
**Type:** Kafka sink connector (plugin for Kafka Connect)

## Overview
Kafka Connect Milvus Connector is a Kafka sink connector that streams vector data from Kafka topics into Milvus-based vector databases, including self-hosted Milvus and Zilliz Cloud. It is designed to build real-time vector data ingestion pipelines where Kafka messages are written directly into Milvus collections.

## Features
- **Kafka sink connector for Milvus**  
  - Streams data from Kafka topics into Milvus collections.

- **Vector data ingestion**  
  - Supports ingestion of vector data into Milvus or Zilliz Cloud.  
  - Targets collections that contain exactly one vector field and optional scalar fields.

- **Schema alignment between Kafka and Milvus**  
  - Requires Kafka message schema to match the Milvus collection schema.  
  - Enforces one and only one vector field in the schema.  
  - Supports zero or more scalar fields (e.g., string, integer, float).  
  - Field names must match exactly between Kafka messages and Milvus collection.

- **Deployment targets**  
  - Works with Confluent Cloud (hosted Kafka).  
  - Works with open-source Kafka clusters.  
  - Writes to self-hosted Milvus or Zilliz Cloud.

- **Plugin packaging**  
  - Distributed as a plugin zip (e.g., `zilliz-kafka-connect-milvus-xxx.zip`) for Kafka Connect.

- **Real-time streaming pipelines**  
  - Designed for real-time or near real-time streaming of vector data from Kafka into Milvus.

## Requirements & Usage Notes
- Need a running Kafka environment (Confluent Cloud or open-source Kafka).
- Need a Milvus or Zilliz Cloud instance with collections defined.  
- Kafka topic messages must use a schema that matches the target Milvus collection (same fields, same names, one vector field).

## Pricing
- Not specified in the provided content. The connector is hosted on GitHub and appears as an open-source project; consult the repository and license file for details.

## Resources
- **Source code & documentation:** https://github.com/zilliztech/kafka-connect-milvus
- **Image (pipeline diagram):** https://raw.githubusercontent.com/zilliztech/kafka-connect-milvus/main/docs/images/kafka-milvus-pipeline.png
