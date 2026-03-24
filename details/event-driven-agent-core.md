## Overview

Event-Driven Agent Core is an architectural pattern where agents respond to events (messages, state changes, external triggers) rather than continuously polling or running in loops.

## Key Characteristics

- Agents sleep until events arrive
- Asynchronous message passing
- Reactive rather than proactive execution
- Resource-efficient
- Scalable to many agents

## AG2 Implementation

AG2's v0.4 rewrite features an event-driven core with:
- Async-first execution model
- Event bus for agent communication
- Pluggable orchestration strategies
- Non-blocking operations

## Benefits

- **Efficiency**: Agents don't waste CPU when idle
- **Scalability**: Support thousands of concurrent agents
- **Responsiveness**: React immediately to events
- **Composability**: Easy to add new event handlers
- **Debugging**: Clear event traces

## Comparison to Traditional

### Polling-Based
- Agents run in loops
- High CPU usage even when idle
- Harder to coordinate
- Simpler to understand

### Event-Driven
- Agents react to events
- Low CPU when idle
- Better coordination
- Requires async programming

## Use Cases

- Multi-agent systems
- Microservices architectures
- Real-time applications
- High-concurrency systems

## Pricing

Architectural pattern, implemented in AG2.