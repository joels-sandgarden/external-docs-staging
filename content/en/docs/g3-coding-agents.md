---
title: Coding Agents
url: "docs/coding-agents"
description: "Two ways a coding agent works with Doc Holiday: the plugin, or the API."
---

Doc Holiday keeps your documentation aligned with your code as it ships. Coding agents — the assistants and CLIs your team already runs — can request that work directly, so a documentation update is filed the moment the code that needs it lands.

There are two ways an agent works with Doc Holiday. Pick based on how much you want the agent to do.

## Install the plugin

Install the **Doc Holiday plugin** and your agent gains Doc Holiday's documentation **skills** plus a set of **MCP tools** for driving the service — planning a site, generating pages, and tracking work — without writing any HTTP calls yourself. This is the path for an agent that actively helps you plan and produce docs.

- [Install the Doc Holiday plugin](./g5-install-plugin.md) — set it up in Claude Code, Codex, OpenCode, or Cursor.
- [Plan and generate docs with skills](./g6-plan-generate-with-skills.md) — take a codebase to a planned, generated docs site.

## Call the API directly

Any agent with shell or HTTP access can file a request without the plugin, by calling the Doc Holiday REST API. This is the path for a lightweight, scripted "when code changes, ask for a docs update" step in an agent's standing instructions.

- [Request docs via the API](./g7-request-docs-api.md) — the one REST call, plus a drop-in rule for your agent.

Both paths file the same kind of work request, staged for human review before anything reaches your repository.
