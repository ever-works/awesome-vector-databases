## Amazon RDS for PostgreSQL

Amazon RDS for PostgreSQL is a managed relational database service from AWS that hosts PostgreSQL, including specific community versions. It simplifies setting up, operating, and scaling PostgreSQL deployments on the cloud, managing administrative tasks like software installation, upgrades, storage, replication, and backups. It supports PostgreSQL 11 through 17 and allows building high-performance extensions with Trusted Language Extensions (TLE).

### Features
*   **Easier, managed deployments:** Launch and connect to production-ready PostgreSQL databases with preconfigured parameters. Offers granular control via database parameter groups and safer updates with Amazon RDS Blue/Green Deployments.
*   **Fast, predictable storage:** Provides SSD-backed storage options: General Purpose for cost-effective workloads and Provisioned IOPS for high-performance OLTP applications (up to 40,000 IOs per second). Storage can be provisioned on the fly with zero downtime.
*   **Backup and recovery:** Automated backup feature allows recovery to any point in time within a 35-day retention period. User-initiated full database backups are also supported.
*   **High availability and read replicas:** Amazon RDS Multi-AZ deployments enhance availability and durability for production workloads. Amazon RDS Read Replicas enable elastic scaling for read-heavy database workloads.
*   **Isolation and security:** Offers network isolation using Amazon Virtual Private Cloud (VPC), encryption at rest with AWS Key Management Service (KMS), and encryption of data in transit using SSL.
*   **Version Support:** Supports PostgreSQL versions 11, 12, 13, 14, 15, 16, and 17.
*   **Trusted Language Extensions (TLE):** Allows building and safely running high-performance extensions on RDS using popular trusted languages without AWS certification.
*   **pgvector Support:** Native extension for vector storage and similarity search (cosine, L2, inner product).
*   **Row Level Security (RLS):** Built-in Postgres feature for multi-tenant isolation.

### Use Cases
- Multi-tenant AI applications with vector search and relational data
- RAG systems requiring SQL joins on embeddings
- Enterprise apps needing ACID compliance with semantic search

## Comparisons

**Managed Postgres + pgvector vs Dedicated Vector DBs:**

| Feature | RDS Postgres + pgvector | Dedicated Vector DBs (e.g., Pinecone) |
|---------|------------------------|--------------------------------------|
| SQL Power | Full relational SQL, joins, analytics | Limited SQL or none |
| Transactions | ACID | Often eventual consistency |
| Ecosystem | Postgres extensions/tools | Specialized SDKs |
| Scaling | Read replicas, Multi-AZ | Auto-scaling shards |
| Serverless | Aurora Serverless option | Native serverless |

### Pricing
Managed service pricing based on instance size, storage, I/O. pgvector free. Serverless v2 variant offers pay-per-use. See AWS pricing calculator.