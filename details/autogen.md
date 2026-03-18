## Overview

AutoGen is an open-source programming framework from Microsoft Research for building AI agents and facilitating cooperation among multiple agents to solve tasks. It offers a unified multi-agent conversation framework as a high-level abstraction for using foundation models.

## Features

- **Customizable Agents**: Agents integrate LLMs, tools, and humans via automated agent chat
- **Multiple Conversation Patterns**: Supports two-agent chat, sequential chat (chained conversations), and group chat (3+ agents)
- **Automated Collaboration**: Agents can collectively perform tasks autonomously or with human feedback
- **Tool Integration**: Agents can use tools via code execution
- **Asynchronous Architecture**: Version 0.4 features event-driven, asynchronous messaging for better scalability
- **AutoGen Studio**: No-code GUI for building multi-agent applications

## Conversation Patterns

- **Two-agent chat**: Simple conversation between two agents
- **Sequential chat**: Sequence of chats between two agents, chained by a carryover mechanism
- **Group chat**: Single chat involving more than two agents with dynamic speaker selection

## Use Cases

The framework has demonstrated effectiveness across various domains:
- Mathematics problem solving
- Code generation and debugging
- Question-answering systems
- Supply-chain optimization
- Online decision-making
- Content generation

## Architecture

AutoGen v0.4 features an asynchronous, event-driven architecture with:
- Asynchronous messaging between agents
- Support for both event-driven and request/response patterns
- Improved scalability and performance

## Pricing

Free and open-source under the Apache 2.0 license.