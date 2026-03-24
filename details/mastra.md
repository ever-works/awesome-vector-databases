## Overview

Observational Memory (OM) is a memory system developed by Mastra that achieves 94.87% on LongMemEval with GPT-5-mini (the highest score ever recorded on this benchmark) and 84.23% with GPT-4o, beating the previous state-of-the-art.

## How It Works

The architecture uses two background agents (Observer and Reflector) that watch conversations and maintain a dense text-only observation log that replaces raw message history as it grows. The context window is broken into two blocks: the first is the list of observations, and the second is raw messages that haven't yet been compressed.

When messages hit 30k tokens (configurable threshold), a separate "observer agent" compresses messages into new observations that are appended to the first block. When observations hit 40k tokens (also configurable), a separate "reflector agent" garbage collects observations that don't matter.

## Key Features

- The compression is typically 5–40×
- Completely stable context window that's predictable, reproducible, and prompt-cacheable across many agent/user turns
- Completely open source end to end
- Uses formatted text rather than structured objects, as it's easier to use, optimized for LLMs, and far easier to debug

## Announcement and Availability

The system was announced in February 2026 and is available for use with Mastra's agent framework.

## Pricing

Open-source framework.