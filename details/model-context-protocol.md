## Overview

The Model Context Protocol (MCP) is an open standard and open-source framework introduced by Anthropic in November 2024 to standardize the way artificial intelligence (AI) systems like large language models (LLMs) integrate and share data with external tools, systems, and data sources.

## Major 2025-2026 Developments

**Donation to Linux Foundation (December 2025)**
Anthropic donated the Model Context Protocol (MCP) to the Agentic AI Foundation (AAIF), a directed fund under the Linux Foundation, co-founded by Anthropic, Block and OpenAI, with support from Google, Microsoft, Amazon Web Services (AWS), Cloudflare, and Bloomberg.

**Industry Adoption**
Following its announcement, the protocol was adopted by major AI providers, including OpenAI and Google DeepMind. In March 2025, OpenAI adopted MCP across the Agents SDK, Responses API, and ChatGPT desktop, and in April 2025, Google DeepMind's Demis Hassabis confirmed MCP support in upcoming Gemini models.

**Growth Metrics**
Claude now has a directory with over 75 connectors powered by MCP, and there are official SDKs for MCP in all major programming languages with 97M+ monthly SDK downloads across Python and TypeScript.

## Technical Features

Model Context Protocol (MCP) is an open protocol that enables seamless integration between LLM applications and external data sources and tools. The November 25th spec release introduced many new features, including asynchronous operations, statelessness, server identity, and official extensions.

## Security Considerations

In April 2025, security researchers released an analysis that concluded there are multiple outstanding security issues with MCP, including prompt injection, tool permissions that allow for combining tools to exfiltrate data, and lookalike tools that can silently replace trusted ones.

## Integration

- Graphiti includes a Model Context Protocol (MCP) server, giving Claude, Cursor, and other MCP clients knowledge graph-based memory
- E2B sandboxes include direct access to Docker's MCP Catalog with 200+ tools
- Supported by major frameworks and platforms

## Pricing

Open-source protocol, free to implement.