## Overview

Perpetual Sandbox is an architecture that maintains complete filesystem and memory state indefinitely without compute charges during idle periods, while enabling rapid resume from standby.

## Key Characteristics

- State persists across hibernation periods
- Sub-25ms resume times from standby
- Zero compute charges during idle
- Infinite standby duration
- Complete memory and filesystem preservation

## Technical Implementation

Perpetual sandboxes use:
- MicroVM technology for hardware isolation
- Memory snapshots for fast state restoration
- Automatic hibernation after brief inactivity (15 seconds)
- Efficient state serialization

## Cost Model

This eliminates the cost tension between instant availability and paying for unused infrastructure. Teams pay only for active compute time while dormant standby periods incur no charges.

## Use Cases

The perpetual standby architecture works particularly well for:
- Coding assistants with unpredictable usage
- PR review automation
- Data analysis agents
- Development environments
- Long-running agent workflows

## Comparison to Traditional Approaches

- **Always-on**: Expensive, wasteful for bursty workloads
- **Cold-start**: Slow startup, poor user experience
- **Perpetual**: Best of both worlds

## Pricing

Implementation pattern, Blaxel offers commercial perpetual sandboxes.