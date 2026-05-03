## Overview

CLI tool for managing RuVector databases and integrations like hooks for self-learning AI.

## Features

- Database init, insert, search
- Hooks for Claude Code integration
- Shell completions
- PostgreSQL support

## Usage

```bash
cargo install ruvector-cli
ruvector init mydb --dim 1536
ruvector insert mydb --file embeddings.json
ruvector search mydb --query "[0.1, 0.2, ...]" --limit 10
ruvector hooks init
```

## Pricing

Open-source, free.