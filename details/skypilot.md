## Overview

SkyPilot is an open-source framework designed for running AI workloads, batch inference, and distributed training on any cloud infrastructure. It provides automated resource provisioning across multiple cloud regions and providers, enabling access to hundreds of GPUs simultaneously.

## Key Capabilities

- Multi-cloud GPU orchestration across AWS, GCP, Azure, and other providers
- Automatic cross-region scheduling based on GPU availability and pricing
- Spot/preemptible instance support with checkpoint-and-resume capabilities
- Distributed embedding pipeline coordination for large-scale inference
- Resource optimization through regional price arbitrage

## Use Cases

- Large-scale embedding generation: Documented deployment using 406 L4 GPUs achieved 364,400 tokens/sec throughput, reducing 20-hour processing jobs to 2.3 hours
- Batch inference workloads that tolerate interruption, benefiting from spot pricing (~61% cost reduction)
- Cross-cloud workload distribution to avoid GPU capacity constraints

## Pricing

Free and open-source software. Users pay only for underlying cloud infrastructure. Spot instances can reduce compute costs by up to 61% compared to on-demand pricing.