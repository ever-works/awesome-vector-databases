## Overview

Letta (originally known as MemGPT) is the platform for building stateful agents: AI with advanced memory that can learn and self-improve over time. Letta emerged from stealth with $10M in funding to build AI agents with advanced memory.

## Core Architecture

Letta takes an OS-inspired approach where main context acts as RAM (fast, limited) and external storage as disk (slow, unlimited), with the agent deciding when to page information in and out.

In Letta, all state, including memories, user messages, reasoning, and tool calls, are persisted in a database so they are never lost, even once evicted from the context window.

## Key Features in 2026

1. **Memory Management**: Agents control their own memory through function calls - reading, writing, searching, and archiving information explicitly, enabling effectively unlimited memory despite fixed context window constraints.

2. **Model Agnostic**: Letta is fully model-agnostic, though they recommend Opus 4.5 and GPT-5.2 for best performance.

3. **Persistent State**: Unlike basic agents that forget when their context window fills up, Letta agents maintain memories across sessions and continuously improve, even while they sleep.

4. **Memory Blocks**: Memory blocks are pieces of context (strings) that are editable by agents via memory tools. Memory blocks that are attached to an agent are in-context (pinned to the system prompt).

## 2026 Market Position

For developers in 2026, pick Letta for long-running agents that need unlimited memory. Recent comparisons place Letta among the top AI agent memory frameworks alongside Mem0, Zep, Cognee, LangChain Memory, and LlamaIndex Memory.

## Pricing

Contact for enterprise pricing.