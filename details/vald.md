# Vald

[Vald](https://vald.vdaas.org/) is an open-source, highly scalable distributed vector search engine designed for fast approximate nearest neighbor (ANN) search on dense vector data. Built on a cloud-native architecture, Vald enables efficient, real-time large-scale vector search operations.

## Features
- **Highly Scalable Distributed Architecture:** Designed for horizontal scaling across memory and CPU, capable of handling billions of feature vectors.
- **Fast ANN Search:** Utilizes the NGT (Neighborhood Graph and Tree) algorithm for efficient approximate nearest neighbor searches.
- **Asynchronous Auto-Indexing:** Supports non-blocking, distributed auto-indexing, allowing the system to remain operational during indexing processes.
- **Automatic Index Backup:** Offers auto-backup capabilities using object storage or persistent volumes for disaster recovery.
- **Distributed Indexing:** Distributes vector indices across multiple agents, each storing different parts of the index.
- **Index Replication and Rebalancing:** Stores index replicas on multiple agents and can automatically rebalance replicas if an agent fails.
- **Customizable Ingress/Egress Filtering:** Provides configurable filters for data input/output, adaptable to gRPC interfaces.
- **Multi-language SDKs:** Supports SDKs for Golang, Java, Node.js, and Python.
- **Highly Customizable:** Allows configuration of vector dimensions, number of replicas, and other advanced settings.
- **Easy Installation:** Designed for quick and simple deployment.

## Category
- Vector Database Engines

## Tags
- open-source
- distributed
- scalable
- real-time

## Pricing
No pricing information was provided; Vald is open-source.
