# Connections API reference

This page covers direct integration with Doc Holiday's API.

Use this reference when an integration needs to create, read, update, delete, sync, or inspect connection records. `/j8-connection-types.md` lists every connection type.

## Authentication

Every endpoint below requires an SFS token. The server uses `AuthHandler: APIServer.authSFSToken` on each route.

## Shared response shape

Connection responses include these fields:

- `allowedTriggerEvents`
- redacted `config`
- `healthy`
- `paused`
- `createdAt`
- `updatedAt`
- `deletedAt`

List responses add `nextPageToken` and `previousPageToken` when the schema includes them. The list payload name changes by route: `connections`, `channels`, `repos`, or `statuses`.

## Success status summary

| Method and path | Success status |
| --- | --- |
| `POST /api/v1/connections` | `201 Created` |
| `GET /api/v1/connections` | `200 OK` |
| `GET /api/v1/connections/{id}` | `200 OK` |
| `PUT /api/v1/connections/{id}` | `200 OK` |
| `DELETE /api/v1/connections/{id}` | `204 No Content` |
| `POST /api/v1/connections/{id}/sync` | `202 Accepted` |
| `GET /api/v1/connections/{id}/health` | `200 OK` |
| `GET /api/v1/connections/{id}/channels` | `200 OK` |
| `GET /api/v1/bitbucket/repos` | `200 OK` |
| `GET /api/v1/connections/{id}/jira/statuses` | `200 OK` |
| `POST /api/v1/connections/{id}/merges/summarize` | `202 Accepted` |

## Connection config examples

The `config` field uses a single-variant object with one sub-object per connection type.

### `githubRepo`

```json
{
  "githubRepo": {
    "githubAppConnectionId": "12",
    "repositoryUrl": "https://github.com/example/docs"
  }
}
```

### `notion`

```json
{
  "notion": {
    "integrationKey": "secret-key"
  }
}
```

### `slackChannel`

```json
{
  "slackChannel": {
    "slackAppConnectionId": "9",
    "channelId": "C01234567"
  }
}
```

## Endpoint reference

### `POST /api/v1/connections`

Create a new connection record.

| Key | Value |
| --- | --- |
| Body | `name`, `config` |
| Success | `201 Created` |
| Common errors | `400` when `config` is missing or more than one connection variant appears |

```bash
curl -X POST "https://api.doc.holiday/api/v1/connections" \
  -H "Authorization: Bearer $SFS_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"name":"Docs GitHub","config":{"githubRepo":{"githubAppConnectionId":"12","repositoryUrl":"https://github.com/example/docs"}}}'
```

```json
{
  "name": "Docs GitHub",
  "config": {
    "githubRepo": {
      "githubAppConnectionId": "12",
      "repositoryUrl": "https://github.com/example/docs"
    }
  }
}
```

The API validates that `config` contains exactly one variant before it stores the record. A request that omits `config` or includes more than one variant fails with `400`.

### `GET /api/v1/connections`

List connection records.

| Key | Value |
| --- | --- |
| Query parameters | `name`, `type`, `paused`, `syncedAtBefore`, `remainingRateLimitPercent`, `healthy` |
| Returns | `connections` |
| Success | `200 OK` |

```bash
curl "https://api.doc.holiday/api/v1/connections?name=Docs&healthy=true" \
  -H "Authorization: Bearer $SFS_TOKEN"
```

```json
{
  "connections": [
    {
      "id": "123",
      "orgId": "org_1",
      "name": "Docs GitHub",
      "type": "githubRepo",
      "healthy": true,
      "paused": false,
      "config": {
        "githubRepo": {
          "githubAppConnectionId": "12",
          "repositoryUrl": "https://github.com/example/docs"
        }
      },
      "createdAt": "2026-07-21T12:00:00Z",
      "updatedAt": "2026-07-21T12:00:00Z"
    }
  ],
  "nextPageToken": "token-2",
  "previousPageToken": "token-1"
}
```

List responses keep the same connection shape as `GET /api/v1/connections/{id}` and add pagination tokens when more pages exist.

### `GET /api/v1/connections/{id}`

Retrieve one connection record.

| Key | Value |
| --- | --- |
| Path parameter | `id` |
| Returns | one connection record |
| Success | `200 OK` |

```bash
curl "https://api.doc.holiday/api/v1/connections/123" \
  -H "Authorization: Bearer $SFS_TOKEN"
```

```json
{
  "id": "123",
  "orgId": "org_1",
  "name": "Docs GitHub",
  "type": "githubRepo",
  "healthy": true,
  "paused": false,
  "config": {
    "githubRepo": {
      "githubAppConnectionId": "12",
      "repositoryUrl": "https://github.com/example/docs"
    }
  },
  "createdAt": "2026-07-21T12:00:00Z",
  "updatedAt": "2026-07-21T12:00:00Z",
  "deletedAt": null
}
```


### `PUT /api/v1/connections/{id}`

Replace a connection record.

| Key | Value |
| --- | --- |
| Path parameter | `id` |
| Body | `name`, `paused`, `config` |
| Success | `200 OK` |
| Common errors | `400` when `config` is missing or more than one connection variant appears |

```bash
curl -X PUT "https://api.doc.holiday/api/v1/connections/123" \
  -H "Authorization: Bearer $SFS_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"name":"Docs GitHub","paused":false,"config":{"githubRepo":{"githubAppConnectionId":"12","repositoryUrl":"https://github.com/example/docs"}}}'
```

```json
{
  "name": "Docs GitHub",
  "paused": false,
  "config": {
    "githubRepo": {
      "githubAppConnectionId": "12",
      "repositoryUrl": "https://github.com/example/docs"
    }
  }
}
```

The API replaces the stored fields with the request body. It uses the same one-of validation as create.

### `DELETE /api/v1/connections/{id}`

Delete a connection record.

| Key | Value |
| --- | --- |
| Path parameter | `id` |
| Query parameter | `preserveDependencies` |
| Success | `204 No Content` |

```bash
curl -X DELETE "https://api.doc.holiday/api/v1/connections/123?preserveDependencies=true" \
  -H "Authorization: Bearer $SFS_TOKEN"
```

```json
{
  "error": "..."
}
```

Success returns `204 No Content` and no response body.

### `POST /api/v1/connections/{id}/sync`

Start a background sync for the connection.

| Key | Value |
| --- | --- |
| Path parameter | `id` |
| Body | `wait`, `timeout` |
| Success | `202 Accepted` |

```bash
curl -X POST "https://api.doc.holiday/api/v1/connections/123/sync" \
  -H "Authorization: Bearer $SFS_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"wait":true,"timeout":30}'
```

```json
{
  "wait": true,
  "timeout": 30
}
```

The API accepts the request and starts background work. `wait` controls whether the call waits for completion, and `timeout` caps that wait.

### `GET /api/v1/connections/{id}/health`

| Key | Value |
| --- | --- |
| Path parameter | `id` |
| Success | `200 OK` |

### `GET /api/v1/connections/{id}/channels`

| Key | Value |
| --- | --- |
| Path parameter | `id` |
| Returns | `channels` |
| Success | `200 OK` |

### `GET /api/v1/bitbucket/repos`

| Key | Value |
| --- | --- |
| Query parameters | `connectionId`, `workspace`, `token` |
| Returns | `repos` |
| Success | `200 OK` |

### `GET /api/v1/connections/{id}/jira/statuses`

| Key | Value |
| --- | --- |
| Path parameter | `id` |
| Returns | `statuses` |
| Success | `200 OK` |

### `POST /api/v1/connections/{id}/merges/summarize`

| Key | Value |
| --- | --- |
| Path parameter | `id` |
| Body | `number` |
| Success | `202 Accepted` |
