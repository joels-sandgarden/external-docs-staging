# Connections API reference

This page covers direct integration with Doc Holiday's API.

Use this reference when an integration needs the public Connections endpoints. See [/j8-connection-types.md](/j8-connection-types.md) for the full type list.

## Common shapes

- Every endpoint requires an SFS token.
- `config` is a one-of object. `POST /api/v1/connections` and `PUT /api/v1/connections/{id}` return `400` when `config` is missing or when more than one variant is set.
- Connection responses include `id`, `orgId`, `name`, `type`, `allowedTriggerEvents`, `healthy`, `paused`, redacted `config`, `createdAt`, `updatedAt`, and `deletedAt`.
- List responses return `connections`, `channels`, `repos`, or `statuses`, and include `nextPageToken` and `previousPageToken` when present.

### Config examples

#### `githubRepo`

```json
{
  "githubRepo": {
    "githubAppConnectionId": "12",
    "repositoryUrl": "https://github.com/example/docs"
  }
}
```

#### `notion`

```json
{
  "notion": {
    "integrationKey": "secret-key"
  }
}
```

#### `slackChannel`

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
