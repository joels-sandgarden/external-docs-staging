---
title: Public MCP Server
slug: "docs/public-mcp-server"
description: "The `/mcp` endpoint for direct integration with external MCP clients."
---

This page describes the `/mcp` endpoint as a direct integration point for external MCP clients.

## Overview

External MCP clients use `/mcp` when they need to request documentation work without installing the plugin. The endpoint gives direct access to Doc Holiday from tools that already speak MCP.

For the full plugin tool reference, see [MCP Tools](./j12-mcp-tools.md).

## Authentication

The endpoint accepts a Doc Holiday API key as a Bearer token in `Authorization: Bearer <token>`.

## Transport

The server stays stateless and serves MCP traffic over streamable HTTP. Each request stands on its own, so clients can reconnect without keeping session state on the server.

## Tool surface

The public endpoint groups its surface into four capabilities:

- Request submission: start a new documentation request or extend an existing one.
- Work tracking: check the current state of a request and follow its history.
- Content review: read turns, comments, and diffs attached to a request.
- Publication lookup: resolve the publication that the request targets.

## Related

- [MCP Tools](./j12-mcp-tools.md) — the plugin-installed tool reference with the full `doc_holiday_*` list and arguments.
- [Coding Agents](./g3-coding-agents.md) — the overview of the plugin path and direct API access.
- [Request Docs via the API](./g7-request-docs-api.md) — the REST path for agents that do not need MCP.
- [API Overview](./j1-api-overview.md) — the shared authentication and API contract reference.