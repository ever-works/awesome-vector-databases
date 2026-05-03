## Overview

RuVix thinks in vectors, graphs, proofs, and capabilities for native AI support.

## Primitives

| Primitive | Purpose | Status |
|-|-|-|
| Task | Concurrent execution with capability set | ✅ Implemented |
| Capability | Unforgeable access token (seL4-inspired) | ✅ Implemented |
| Region | Memory with policy (immutable/append/slab) | ✅ Implemented |
| Queue | io_uring-style lock-free IPC | ✅ Implemented |
| Timer | Deadline-driven scheduling | ✅ Implemented |
| Proof | Cryptographic attestation for mutations | ✅ Implemented |

Phases A-F complete with 20+ crates, 1,200+ tests.

## Developer Tools

- ruvix build: Cross-compile for AArch64
- ruvix flash: Flash to SD card
- ruvix keys: Ed25519 key management
- etc.

## Pricing

Free and open-source.