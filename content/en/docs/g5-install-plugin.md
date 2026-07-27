---
title: Install the Doc Holiday Plugin
url: "docs/install-the-doc-holiday-plugin"
description: "Install the Doc Holiday plugin in Claude Code, Codex, OpenCode, or Cursor."
---

The Doc Holiday plugin gives your coding agent Doc Holiday's documentation **skills** and a set of **MCP tools** for driving the service. One plugin serves several agents — Claude Code, OpenAI Codex, OpenCode, and Cursor — from a single published source.

Installing the plugin also registers Doc Holiday's hosted MCP server. The server is protected by sign-in: the first tool call opens a one-time browser authorization, after which your agent is connected to your organization.

Pick your agent below. Unless noted, each command runs inside that agent.

## Claude Code

```text
/plugin marketplace add sandgardenhq/doc-holiday
/plugin install doc-holiday@doc-holiday
```

The first command registers the marketplace; the second installs the plugin — its skills plus the MCP server. Restart Claude Code if prompted. The first tool call opens a one-time browser sign-in.

## OpenAI Codex

Add the marketplace from your shell:

```bash
codex plugin marketplace add sandgardenhq/doc-holiday
```

Then, inside Codex, run `/plugins` and install **doc-holiday**. Finally, complete the one-time sign-in from your shell:

```bash
codex mcp login doc-holiday
```

## OpenCode

OpenCode has no marketplace — add Doc Holiday as a plugin in your `opencode.json` (global `~/.config/opencode/opencode.json` or a project-local `opencode.json`), then restart OpenCode:

```json
{ "plugin": ["doc-holiday@git+https://github.com/sandgardenhq/doc-holiday.git"] }
```

The first tool call opens a one-time browser sign-in. Pin a version with a git ref (`…/doc-holiday.git#v0.3.2`).

## Cursor

Cursor has a plugin marketplace, but no individual-user "add a marketplace repo" command yet. Clone the repo and symlink the plugin into Cursor's local plugins directory:

```bash
git -C ~/.cursor/plugins/sources/doc-holiday pull || git clone https://github.com/sandgardenhq/doc-holiday.git ~/.cursor/plugins/sources/doc-holiday
mkdir -p ~/.cursor/plugins/local
ln -sf ~/.cursor/plugins/sources/doc-holiday/plugins/doc-holiday ~/.cursor/plugins/local/doc-holiday
```

Open Cursor's Customize sidebar → Plugins and enable **doc-holiday**. The first tool call opens a one-time browser sign-in.

If your organization is on a Cursor Team or Enterprise plan, an admin can import the repo once for everyone: Dashboard → Settings → Plugins → Team Marketplaces → Import → `sandgardenhq/doc-holiday`.

## Update the plugin

| Agent | Command |
| --- | --- |
| Claude Code | `/plugin marketplace update doc-holiday`, then `/reload-plugins` |
| OpenAI Codex | `codex plugin marketplace upgrade doc-holiday` (restart Codex) |
| OpenCode | `rm -rf ~/.cache/opencode/node_modules/doc-holiday` and restart |
| Cursor | `git -C ~/.cursor/plugins/sources/doc-holiday pull` |

## Next

- [Plan and generate docs with skills](./g6-plan-generate-with-skills.md) — put the skills to work.
- [MCP tools reference](./j12-mcp-tools.md) — the tools the plugin registers.
