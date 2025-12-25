# tinyvector

**Category:** Vector Database Engines  
**Website/Source:** https://github.com/0hq/tinyvector

## Description

tinyvector is a minimal vector database / approximate nearest neighbor (ANN) engine built with SQLite and PyTorch. It is focused on simplicity and compact implementation for educational use and small-scale similarity search applications. The project is currently in pre-release and still under active development.

## Features

- Minimal vector database / ANN engine
- Designed for educational and small-scale similarity search use cases
- Built on top of **SQLite** for storage
- Uses **PyTorch** in its implementation
- Provides a server that can be run manually
- Test suite available for validation and development
- Multi-language ecosystem:
  - Python implementation: `tinyvector` (this repository)
  - Rust implementation: [`tinyvector-rs`](https://github.com/m1guelpf/tinyvector-rs)

### Development status
- Pre-release, not yet production-ready
- Aiming for production readiness in a future release (timeline indicated as late July in the repository, subject to change)

## Usage

Basic commands from the repository:

```bash
# Run the server manually
pip install -r requirements.txt
python -m server

# Run tests
pip install pytest pytest-mock
pytest
```

## Pricing

- Open-source project (license present in repository).  
  No paid pricing plans are listed in the available content.