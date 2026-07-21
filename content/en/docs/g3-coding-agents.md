---
title: Coding Agents
url: "docs/coding-agents"
description: "Let coding agents request documentation work."
---

Doc Holiday keeps documentation aligned with shipped behavior when code changes. This guide covers the REST request a coding agent sends directly when code changes need a matching documentation update.

Any coding agent with tool or script access can use this REST API.

## Request the work

1. Send a `POST /api/v1/conversations/` request with a Doc Holiday API key in `Authorization: Bearer <token>`.
2. Set `stage: true` by default.
3. Include `body`, `publication`, and `stage`.

### curl

```bash
curl -X POST 'https://api.doc.holiday/api/v1/conversations/' \
  -H 'Authorization: Bearer <token>' \
  -H 'Content-Type: application/json' \
  -d '{
    "body": "Update the authentication guide for the new token flow.",
    "publication": "docs-site",
    "stage": true
  }'
```

### JSON payload

```json
{
  "body": "Update the authentication guide for the new token flow.",
  "publication": "docs-site",
  "stage": true
}
```

## Agent rules snippet

Drop a block like this into your agent's standing instructions (`CLAUDE.md`, agent rules, or the equivalent):

```text
When you change user-visible behavior in this repo (API shape, CLI flags,
configuration, workflows), file a documentation request with Doc Holiday
after the change merges:

  curl -X POST 'https://api.doc.holiday/api/v1/conversations/' \
    -H "Authorization: Bearer $DOC_HOLIDAY_API_KEY" \
    -H 'Content-Type: application/json' \
    -d '{"body": "<what changed and which page to update, with a PR link>", "publication": "<publication name>", "stage": true}'

Rules:
- One request per distinct documentation change; batch nothing.
- Name the outcome and the page: "Update /docs/auth.md for the new token flow (PR #123)".
- Keep "stage": true — a human reviews the draft before anything reaches the docs repo.
- File once per change; duplicate requests create duplicate work items.
```

## Review by default

Setting `stage: true` keeps the request in Work History, staged for human review, before anything is opened against your repository.

## Reference

For the complete Work History API resource, see [Work History API reference](./j4-api-work-history.md).

## Coming soon

A first-party MCP endpoint is coming soon.