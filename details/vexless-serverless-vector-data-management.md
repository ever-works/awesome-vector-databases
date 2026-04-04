## Overview

Vexless is a serverless vector data management system introduced at SIGMOD 2024, leveraging cloud functions for elastic and cost-effective vector similarity search.

## Architecture

- **Serverless Design**: Built on cloud functions for auto-scaling
- **Compute-Storage Decoupling**: Separate compute and storage layers for cost efficiency
- **Pay-Per-Use Pricing Model**: Scales to zero when idle
- **Stateless Workers**: Compute nodes are stateless, enabling rapid scale-out

## Publication

- **Venue**: SIGMOD 2024
- **Authors**: Su et al.

## Use Cases

- Variable workloads with unpredictable query patterns
- Cost-sensitive vector search applications
- Prototyping and development environments