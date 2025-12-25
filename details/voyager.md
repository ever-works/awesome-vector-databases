## Voyager

**Brand:** Spotify  
**Category:** SDKs & Libraries  
**Website:** https://github.com/spotify/voyager  
**License:** Apache-2.0  
**Type:** Open-source approximate nearest-neighbor (ANN) search library and service

### Overview
Voyager is an open-source vector search library for Python and Java, designed for efficient approximate nearest-neighbor search on large-scale vector datasets. It focuses on ease of use, simplicity, and deployability, and can be used both as an embedded library and as a service.

### Features
- **Approximate nearest-neighbor search** for high-dimensional vectors.
- **Large-scale vector dataset support**, suitable for production-scale search workloads.
- **Multi-language support**:
  - Python bindings
  - Java bindings
  - Core C++ implementation (in `cpp` directory)
- **Library and service modes**:
  - Usable as a library within Python/Java applications
  - Can be deployed as a standalone service for vector search
- **Performance and benchmarking**:
  - Dedicated `benchmarks` directory for performance tests and comparisons
  - Designed for efficient query performance on large indexes
- **Documentation**:
  - `docs` directory with project documentation and usage guidance
- **Project governance and contribution**:
  - `CODE_OF_CONDUCT.md` defining contributor behavior
  - `CONTRIBUTING.md` with contribution guidelines
  - `OWNERS.md` documenting project ownership/maintainers
- **Configuration and tooling**:
  - C++ formatting via `.clang-format`
  - Git submodules defined in `.gitmodules`

*(Note: The GitHub page content snippet does not list detailed APIs or algorithms; those would be found in the repository’s README and docs.)*

### Technology Stack
- Core: C++
- Language bindings: Python, Java
- Repository structure: `cpp/`, `python/`, `java/`, `benchmarks/`, `docs/`

### Pricing
- **Open Source** – Free to use under the Apache-2.0 license.
  - No commercial pricing plans are listed in the provided content.