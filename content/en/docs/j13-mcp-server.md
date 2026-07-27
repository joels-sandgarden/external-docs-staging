---
title: MCP Server
url: "docs/mcp-server"
description: "Reference for Doc Holiday's public MCP server and authentication requirements."
---

This reference covers Doc Holiday's public MCP server and direct integration with its API.

## Overview

Doc Holiday provides a public MCP server over HTTP at `/mcp` for API-key authenticated clients. The server exposes the same `doc_holiday_*` tools documented on [MCP Tools](./j12-mcp-tools.md).

## Authentication

- Use an API key in the `Authorization: Bearer <token>` header.
- Session tokens are not accepted for this endpoint.

## Related links

- [API Overview](./j1-api-overview.md)
- [MCP Tools](./j12-mcp-tools.md)