# IDEA

**Category:** SDKs & Libraries  
**Website/Source:** https://github.com/asaflevi0812/IDEA

## Description
IDEA (Inverted Deduplication-Aware Index) is a research implementation of an index structure designed to improve storage efficiency and query performance for similarity search workloads. It targets high-dimensional vector data and content-addressable data, making it applicable to large-scale vector databases and approximate nearest neighbor (ANN) indexing systems. The codebase accompanies the paper *“Physical vs. Logical Indexing with IDEA: Inverted Deduplication-Aware Index”* (FAST ’24) and builds on the Destor open-source storage system.

## Features
- **Inverted, deduplication-aware index structure** for similarity search workloads.
- **Support for high-dimensional vector data** and content-addressable data.
- **Research implementation of naïve and deduplication-aware indexes**, based on the Destor storage system.
- **Designed for large-scale vector database / ANN indexing scenarios**, focusing on storage efficiency and query performance.
- **Configurable via repository-provided configs**, dataset details, and keyword definitions.
- **Build and automation scripts** for compiling the code and generating build commands.
- **Dependency installation script (`install_dependencies.sh`)** tailored to a clean Ubuntu Server 22.04 LTS environment.

## Technical Requirements
- **Operating system:** Ubuntu Server 22.04 LTS (clean image recommended).
- **Dependencies:** Installed via the provided `install_dependencies.sh` script.
- **Version control:** Git required to clone the repository.

## Pricing
- Open-source research code (no pricing information provided).