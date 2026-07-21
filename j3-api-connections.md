# API: Connections

This page covers direct integration with Doc Holiday's API.

Use this reference when an integration needs the public Connections endpoints. See [/j8-connection-types.md](/j8-connection-types.md) for the full type list.

## Common shapes

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

Creates a connection that Doc Holiday can use to read from or write to an external system.

- Key parameters: `name`, `config`, `paused`, `sync`
- curl:
```bash
curl -X POST "https://api.doc.holiday/api/v1/connections" \
  -H "Authorization: Bearer {{sfsToken}}" \
  -H "Content-Type: application/json" \
  -d '{"name":"Docs repo","paused":false,"sync":true,"config":{"githubRepo":{"githubAppConnectionId":"12","repositoryUrl":"https://github.com/acme/docs"}}}'
```
- JSON:
```json
{"id":"12","name":"Docs repo","type":"githubRepo","healthy":true,"paused":false,"allowedTriggerEvents":["pullRequests","newIssues","issueComments","releases"],"config":{"githubRepo":{"githubAppConnectionId":"12","repositoryUrl":"https://github.com/acme/docs"}}}
```
- Behaviors: Requires an SFS token. Returns `400` when `config` is missing or more than one connection type is set.

### `GET /api/v1/connections`

Lists connections and supports filtering by name, type, pause state, sync time, rate limit, and health.

- Key parameters: `name`, `type`, `paused`, `syncedAtBefore`, `remainingRateLimitPercent`, `healthy`
- Returns: `connections`, plus `nextPageToken` and `previousPageToken` when present
- curl:
```bash
curl "https://api.doc.holiday/api/v1/connections?type=githubRepo&healthy=true" \
  -H "Authorization: Bearer {{sfsToken}}"
```
- JSON:
```json
{"connections":[{"id":"12","name":"Docs repo","type":"githubRepo","healthy":true,"paused":false,"allowedTriggerEvents":["pullRequests","newIssues","issueComments","releases"],"config":{"githubRepo":{"githubAppConnectionId":"12","repositoryUrl":"https://github.com/acme/docs"}}}],"nextPageToken":"eyJ..."}
```
- Behaviors: Requires an SFS token. Returns `400` for invalid filters.

### `GET /api/v1/connections/{id}`

Returns one connection record with the redacted configuration and trigger events it can emit.

- Key parameters: `id`
- Returns: one connection record
- curl:
```bash
curl "https://api.doc.holiday/api/v1/connections/12" \
  -H "Authorization: Bearer {{sfsToken}}"
```
- JSON:
```json
{"id":"12","name":"Docs repo","type":"githubRepo","healthy":true,"paused":false,"allowedTriggerEvents":["pullRequests","newIssues","issueComments","releases"],"config":{"githubRepo":{"githubAppConnectionId":"12","repositoryUrl":"https://github.com/acme/docs"}}}
```
- Behaviors: Requires an SFS token. Returns `400` for an invalid or missing `id`.

### `PUT /api/v1/connections/{id}`

Updates the connection name, pause state, and exactly one connection config variant.

- Key parameters: `id`, `name`, `paused`, `config`
- curl:
```bash
curl -X PUT "https://api.doc.holiday/api/v1/connections/12" \
  -H "Authorization: Bearer {{sfsToken}}" \
  -H "Content-Type: application/json" \
  -d '{"name":"Docs source","paused":true,"config":{"notion":{"integrationKey":"secret-key"}}}'
```
- JSON:
```json
{"id":"12","name":"Docs source","type":"notion","healthy":true,"paused":true,"allowedTriggerEvents":[],"config":{"notion":{"integrationKey":"secret-key"}}}
```
- Behaviors: Requires an SFS token. Returns `400` when `config` is missing, ambiguous, or fails validation.

### `DELETE /api/v1/connections/{id}`

Removes a connection and can keep dependent records when needed.

- Key parameters: `id`, `preserveDependencies`
- Returns: no content
- curl:
```bash
curl -X DELETE "https://api.doc.holiday/api/v1/connections/12?preserveDependencies=true" \
  -H "Authorization: Bearer {{sfsToken}}"
```
- JSON:
```json
null
```
- Behaviors: Requires an SFS token. Returns `204 No Content` with no response body.

### `POST /api/v1/connections/{id}/sync`

Starts a background sync for the selected connection.

- Key parameters: `id`, `wait`
- curl:
```bash
curl -X POST "https://api.doc.holiday/api/v1/connections/cnn-0123456789abcdef/sync" \
  -H "Authorization: Bearer {{sfsToken}}" \
  -H "Content-Type: application/json" \
  -d '{"wait":true}'
```
- Behaviors: Requires an SFS token. Returns `202 Accepted` with no response body; invalid `wait` values return `400`.

### `GET /api/v1/connections/{id}/health`

Checks whether a connection is healthy and returns any message or error when present.

- Key parameters: `id`
- Returns: `id`, `status`, and optional `message`, `error`
- curl:
```bash
curl "https://api.doc.holiday/api/v1/connections/cnn-0123456789abcdef/health" \
  -H "Authorization: Bearer {{sfsToken}}"
```
- JSON:
```json
{"id":"cnn-0123456789abcdef","status":"healthy"}
```
- Behaviors: Requires an SFS token. Returns `400` for an invalid or missing `id`.

### `GET /api/v1/connections/{id}/channels`

Lists the channels that the selected connection can reach.

- Key parameters: `id`
- Returns: `channels`
- curl:
```bash
curl "https://api.doc.holiday/api/v1/connections/cnn-0123456789abcdef/channels" \
  -H "Authorization: Bearer {{sfsToken}}"
```
- JSON:
```json
{"channels":[{"id":"C01234567","name":"docs"}]}
```
- Behaviors: Requires an SFS token. Returns `400` for an invalid or unsupported connection.

### `GET /api/v1/bitbucket/repos`

Lists Bitbucket repositories using either a connection ID or workspace credentials.

- Key parameters: `connectionId`, `workspace`, `token`
- Returns: `repos`
- curl:
```bash
curl "https://api.doc.holiday/api/v1/bitbucket/repos?connectionId=cnn-0123456789abcdef" \
  -H "Authorization: Bearer {{sfsToken}}"
```
- JSON:
```json
{"repos":[{"fullName":"acme/docs","slug":"docs"}]}
```
- Behaviors: Use `connectionId` alone, or provide `workspace` and `token` together. Requires an SFS token. Returns `400` for invalid parameters.

### `GET /api/v1/connections/{id}/jira/statuses`

Lists the Jira statuses that a connection can use.

- Key parameters: `id`
- Returns: `statuses`
- curl:
```bash
curl "https://api.doc.holiday/api/v1/connections/cnn-0123456789abcdef/jira/statuses" \
  -H "Authorization: Bearer {{sfsToken}}"
```
- JSON:
```json
{"statuses":[{"id":"100","name":"To Do"},{"id":"101","name":"Done"}]}
```
- Behaviors: Requires an SFS token. Returns `400` for an invalid or missing `id`.

### `POST /api/v1/connections/{id}/merges/summarize`

Starts a background summary for one merged pull request on a connection.

- Key parameters: `id`, `number`
- curl:
```bash
curl -X POST "https://api.doc.holiday/api/v1/connections/cnn-0123456789abcdef/merges/summarize" \
  -H "Authorization: Bearer {{sfsToken}}" \
  -H "Content-Type: application/json" \
  -d '{"number":123}'
```
- Behaviors: Requires an SFS token. Returns `202 Accepted` with no response body; missing or invalid `number` values return `400`.
