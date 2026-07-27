---
title: Coding Agents
url: "docs/coding-agents"
description: "Three ways a coding agent works with Doc Holiday: the plugin, the public MCP server, or the API."
---

Doc Holiday keeps documentation aligned with the code as it ships. Coding agents — the assistants and CLIs a team already runs — can request that work directly, so documentation updates stay tied to the change that needs them.

Doc Holiday offers three integration paths for coding agents. Each path fits a different kind of client and workflow.

## Install the plugin

Install the **Doc Holiday plugin** and the agent gains Doc Holiday's documentation **skills** plus a set of **MCP tools** for planning a site, generating pages, and tracking work without writing any HTTP calls. This path suits an agent that actively helps plan and produce docs inside the plugin.

- [Install the Doc Holiday plugin](./g5-install-plugin.md) — set it up in Claude Code, Codex, OpenCode, or Cursor.
- [Plan and generate docs with skills](./g6-plan-generate-with-skills.md) — take a codebase to a planned, generated docs site.

## Use the public MCP server

The public `/mcp` endpoint suits external MCP clients that need a direct Doc Holiday connection without installing the plugin. It gives agents a standard MCP entry point for documentation requests and related work. See [Public MCP Server](/mcp) for the reference page.

## Call the API directly

Any agent with shell or HTTP access can file a request without the plugin by calling the Doc Holiday REST API. This path suits lightweight, scripted integrations that only need a direct request for a docs update.

- [Request docs via the API](./g7-request-docs-api.md) — the one REST call, plus a drop-in rule for your agent.

All three paths create the same kind of work request, and the request stays in human review before anything reaches the repository.
