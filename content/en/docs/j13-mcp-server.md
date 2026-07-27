---
title: MCP Server
url: "docs/mcp-server"
description: "Direct integration with Doc Holiday's public MCP server and authentication requirements."
---

This page covers direct integration with Doc Holiday's API.

## Overview

The public MCP server is available over HTTP at `/mcp` for API-key authenticated clients. It exposes the same `doc_holiday_*` tool set documented on [MCP Tools](./j12-mcp-tools.md).

## Authentication

- Use an API key in the `Authorization: Bearer <token>` header.
- Session tokens are not accepted for this endpoint.

## Related links

- [API Overview](./j1-api-overview.md)
- [MCP Tools](./j12-mcp-tools.md)