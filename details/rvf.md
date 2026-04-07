## Overview

RVF is an executable knowledge unit, not just a database format. A single .rvf file runs anywhere from browser to bare metal.

## Features

| What It Does | How |
|-|-|
| Self-boot as a microservice | Real Linux kernel in the file, boots in 125 ms on QEMU/KVM |
| Hardware-speed lookups | eBPF programs (XDP, TC, socket filter) bypass userspace |
| Run in any browser | 5.5 KB WASM runtime, zero backend |
| Git-like branching | COW at cluster granularity — 1M vectors, 100 edits = ~2.5 MB child |
| Tamper-evident audit | Hash-linked witness chain for every insert, query, deletion |
| Post-quantum signatures | ML-DSA-65 and Ed25519 signing on every segment |
| DNA-style lineage | Parent/child derivation chains with cryptographic verification |

28 segment types including VEC, INDEX, KERNEL, EBPF, WASM, COW_MAP, WITNESS, CRYPTO, FEDERATED_MANIFEST.

## Installation

```sh
cargo install rvf-cli
cargo add rvf-runtime
npm install @ruvector/rvf
npx @ruvector/rvf-mcp-server --transport stdio
```

## Pricing

Free and open-source.