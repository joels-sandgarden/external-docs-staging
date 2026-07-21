# Coding agents

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

```text
[CLAUDE_SECTION: agent-rules-snippet]
```

## Review by default

That keeps the request in Work History, staged for human review, before it moves on.

## Reference

For the complete Work History API resource, see [Work History API reference](/j4-api-work-history.md).

## Coming soon

A first-party MCP endpoint is coming soon.