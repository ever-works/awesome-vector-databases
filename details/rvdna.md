## Overview

rvDNA puts genomic diagnostics on any device — a phone, a laptop, a browser tab — in 12 milliseconds. Private by default, no cloud or GPU required.

## Features

| What It Does | How |
|-|-|
| Find mutations (sickle cell, cancer) | Bayesian variant calling, 155 ns/SNP |
| Translate DNA to protein | Full codon table + GNN contact graphs |
| Predict biological age | Horvath clock, 353 CpG sites |
| Recommend drug doses | CYP2D6 star alleles + CPIC guidelines |
| Score health risks | 20 SNPs, 6 gene-gene interactions, composite risk scoring in 2 µs |
| Stream biomarker data | Real-time anomaly detection, CUSUM changepoints, >100k readings/sec |
| Search genomes by similarity | HNSW k-mer vectors, O(log N) |
| Store pre-computed AI features | .rvdna binary format — open and instant |

## Installation

```sh
cargo add rvdna              # Rust
npm install @ruvector/rvdna  # JavaScript / TypeScript
```

## Pricing

Free and open-source.