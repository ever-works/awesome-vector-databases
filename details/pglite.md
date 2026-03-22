## Overview

PGLite is a WASM Postgres build packaged into a TypeScript client library that enables you to run Postgres in the browser, Node.js, Bun and Deno, with no need to install any other dependencies. Unlike previous "Postgres in the browser" projects, PGLite does not use a Linux virtual machine - it is simply Postgres in WASM.

## Key Features

- Only 3mb gzipped with support for many Postgres extensions, including pgvector
- Single-process mode that facilitates interaction with PostgreSQL when compiled to WASM
- Full Postgres functionality in environments where Postgres was never supposed to run: browsers, offline apps, developer tools, CI pipelines, edge functions, and local-first systems
- No need for Docker containers or virtual machines

## Technical Implementation

Building upon PostgreSQL's "single user mode," PGLite introduces an input/output pathway that enables interaction with PostgreSQL when compiled to WASM within a JavaScript environment. Programs compiled with Emscripten cannot fork new processes and operate strictly in single-process mode.

## Use Cases

- Testing with real Postgres instead of SQLite
- Offline-first applications
- Browser-based development tools
- Edge computing functions
- CI/CD pipelines without database servers

## Pricing

Free and open-source under the Apache 2.0 license.