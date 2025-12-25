# AHPQ.jl

**Description**

AHPQ.jl is a Julia library implementing the Anisotropic Hierarchical Vector Quantizer based on the Scalable Nearest Neighbours Algorithm (ScaNN). It follows the Google Research implementation (per the referenced paper and talk) and provides a configurable Max Inner Product Search (MIPS) system, written entirely in Julia with no non-Julia dependencies.

- **Category:** SDKs & Libraries
- **Technology:** Julia
- **Use cases:** Vector search, product quantization, MIPS-oriented indexing
- **Source:** https://github.com/AxelvL/AHPQ.jl

---

## Features

- **Anisotropic Hierarchical Vector Quantizer**
  - Implements anisotropic hierarchical product/vector quantization.
  - Trains a vector quantization tree (VQ-tree) with an anisotropic loss function.
  - Optimized for Max Inner Product Search (MIPS) rather than standard L2 distance.

- **ScaNN-based Algorithm**
  - Based on Google Research’s Scalable Nearest Neighbours Algorithm (ScaNN).
  - Follows the approach described in the associated research paper and SlidesLive presentation.

- **IVFADC-style Architecture**
  - Can be viewed as an IVFADC setup (inverted file with asymmetric distance computation).
  - Uses vector quantization for coarse partitioning and refined distance evaluation.

- **Julia-native Implementation**
  - Written 100% in Julia.
  - No non-Julian dependencies, easing installation and integration into Julia projects.

- **Configurable MIPS System**
  - Provides a highly configurable Max Inner Product Search pipeline.
  - Designed for building high-performance vector search systems using product quantization.

*(The repository content snippet does not expose further API-level or configuration details.)*

---

## Pricing

- Not applicable (open-source library; no pricing information provided in the available content).
