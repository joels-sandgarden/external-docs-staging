# Coding agents

Doc Holiday keeps documentation aligned with shipped behavior when code changes. A coding agent that changes code should request the matching documentation work at the same time, so the docs stay current with what shipped.

## Request the work

1. Send a `POST /api/v1/conversations/` request with a Doc Holiday API key in `Authorization: Bearer <token>`.
2. Set `stage: true` by default so a human reviews the staged request.
3. Include `body`, `publication`, and `stage`, and add `changes`, `labels`, or `relevantLinks` when they help a reviewer.

### curl

```bash
curl -X POST 'https://api.doc.holiday/api/v1/conversations/' \
  -H 'Authorization: Bearer <token>' \
  -H 'Content-Type: application/json' \
  -d '{
    "body": "Update the authentication guide for the new token flow.",
    "publication": "docs-site",
    "stage": true,
    "changes": [],
    "labels": ["api"],
    "relevantLinks": ["https://example.com/change"]
  }'
```

### JSON payload

```json
{
  "body": "Update the authentication guide for the new token flow.",
  "publication": "docs-site",
  "stage": true,
  "changes": [],
  "labels": ["api"],
  "relevantLinks": ["https://example.com/change"]
}
```

## Agent rules snippet

```text
[CLAUDE_SECTION: agent-rules-snippet]
```

## Review by default

Set `stage: true` by default. That keeps the request staged for human review before it moves on.

## Reference

For the complete Work History API reference, see [Work History API reference](/j4-api-work-history.md).

## Coming soon

A first-party MCP endpoint is coming soon.