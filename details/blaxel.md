## Overview

Blaxel is a perpetual sandbox platform released on March 11, 2026, coming out of YC's Spring 2025 batch. It maintains sandbox state indefinitely while scaling costs to zero during idle periods, using microVM technology for hardware-level isolation.

## Key Features

**Performance:**
- Blaxel executes agent-generated code in microVMs that resume in under 25 milliseconds
- Sandboxes resume from standby in under 25 milliseconds and automatically scale to zero after a few seconds of inactivity, with sandboxes waiting on standby indefinitely when not used

**State Persistence:**
- Memory state is maintained even after scaling down, including the running processes and entire filesystem
- Perpetual sandbox platforms maintain sandbox state indefinitely while scaling costs to zero during idle periods

**Cost Model:**
This eliminates the cost tension between instant availability and paying for unused infrastructure. Teams pay only for active compute time while dormant standby periods incur no charges.

## Use Cases

The perpetual standby architecture works particularly well for coding assistants, PR review automation, and data analysis agents where unpredictable timing patterns make traditional always-on or cold-start approaches impractical.

## Python SDK

Blaxel's Python SDK lets you create and manage sandboxes and other resources on Blaxel, requiring Python <3.14, >=3.10. The SDK is available on PyPI and can be installed with `pip install blaxel`.

## Security Architecture

Perpetual sandbox platforms like Blaxel use microVM architecture to provide hardware-level isolation for each agent execution environment.

## Integration

Blaxel integrates with the smolagents framework for executing AI agent code securely.

## Pricing

Pay only for active compute time, zero charges during standby periods.