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

| Key | Value |
| --- | --- |
| Body | `name`, `config`, `paused`, `sync` |
| Success | `201 Created` |
| Notes | `config` must set exactly one variant; missing or ambiguous config returns `400` |

### `GET /api/v1/connections`

| Key | Value |
| --- | --- |
| Query parameters | `name`, `type`, `paused`, `syncedAtBefore`, `remainingRateLimitPercent`, `healthy` |
| Returns | `connections` |
| Success | `200 OK` |

### `GET /api/v1/connections/{id}`

| Key | Value |
| --- | --- |
| Path parameter | `id` |
| Returns | one connection record |
| Success | `200 OK` |


### `PUT /api/v1/connections/{id}`

| Key | Value |
| --- | --- |
| Path parameter | `id` |
| Body | `name`, `paused`, `config` |
| Success | `200 OK` |
| Notes | `config` must set exactly one variant; missing or ambiguous config returns `400` |

### `DELETE /api/v1/connections/{id}`

| Key | Value |
| --- | --- |
| Path parameter | `id` |
| Query parameter | `preserveDependencies` |
| Success | `204 No Content` |

```json
null
```

The endpoint returns no body.

### `POST /api/v1/connections/{id}/sync`

| Key | Value |
| --- | --- |
| Path parameter | `id` |
| Body | `wait`, `timeout` |
| Success | `202 Accepted` |

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
