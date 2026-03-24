## Overview

The Observer-Reflector Architecture is a two-agent system used in Mastra's Observational Memory that watches conversations and maintains a compressed text-only observation log.

## Architecture Components

### Observer Agent
When messages hit 30k tokens (configurable threshold), a separate "observer agent" compresses messages into new observations that are appended to the observation block. The compression is typically 5–40×.

### Reflector Agent
When observations hit 40k tokens (also configurable), a separate "reflector agent" garbage collects observations that don't matter, removing outdated or irrelevant information.

## Context Window Structure

The context window is broken into two blocks:
1. **First block**: List of compressed observations
2. **Second block**: Raw messages that haven't yet been compressed

## Key Benefits

- Completely stable context window that's predictable and reproducible
- Prompt-cacheable across many agent/user turns
- Uses formatted text rather than structured objects
- Easier to debug than vector-based approaches

## Performance

Observational Memory achieves 94.87% on LongMemEval with GPT-5-mini, the highest score ever recorded on this benchmark.

## Pricing

Open-source as part of Mastra framework.