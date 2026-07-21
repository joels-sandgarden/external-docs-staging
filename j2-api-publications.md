# Publications API reference

This page covers direct integration with Doc Holiday's API.

Deprecated `/api/v1/automations/*` aliases are covered in `/j1-api-overview.md`.

## Endpoints

### `POST /api/v1/publications`
Creates a publication and returns it with resolved instructions.

| Key parameters | Details |
| --- | --- |
| Body | `name` required; `config` and `instructions` optional |
| Response | `201 Created` |

`curl`: `curl -X POST https://api.doc.holiday/api/v1/publications -H 'Authorization: Bearer $TOKEN' -H 'Content-Type: application/json' -d '{"name":"API Docs","config":{"docsRepo":"pub_1","sourceRepos":["src_1"]}}'`
`JSON`: `{"name":"API Docs","config":{"docsRepo":"pub_1","sourceRepos":["src_1"]},"instructions":[]}`
`Notes`: Permissions gate the call; invalid configs and duplicate names stop the save.

### `GET /api/v1/publications/{id}`
Retrieves one publication with config, health, sync time, and resolved instructions.

| Key parameters | Details |
| --- | --- |
| Path | `id` |
| Response | `200 OK` |

`curl`: `curl -H 'Authorization: Bearer $TOKEN' https://api.doc.holiday/api/v1/publications/pub_1`
`JSON`: `{"id":"pub_1"}`
`Notes`: Access checks run before the lookup; missing or invalid IDs fail the request.

### `GET /api/v1/publications`
Lists publications with paging and filter support.

| Key parameters | Details |
| --- | --- |
| Query | `name`, `syncedAtBefore`, `ids` |
| Response | `200 OK` |

`curl`: `curl -H 'Authorization: Bearer $TOKEN' 'https://api.doc.holiday/api/v1/publications?name=API&ids=pub_1,pub_2'`
`JSON`: `{"name":"API","ids":["pub_1","pub_2"]}`
`Notes`: The result set narrows to permitted publications when broad list access is absent.

### `PUT /api/v1/publications/{id}`
Replaces a publication's full configuration and instruction set.

| Key parameters | Details |
| --- | --- |
| Path | `id` |
| Body | `name` required; `config` and `instructions` optional |
| Response | `200 OK` |

`curl`: `curl -X PUT https://api.doc.holiday/api/v1/publications/pub_1 -H 'Authorization: Bearer $TOKEN' -H 'Content-Type: application/json' -d '{"name":"API Docs","config":{"docsRepo":"pub_1","sourceRepos":["src_1"]}}'`
`JSON`: `{"name":"API Docs","config":{"docsRepo":"pub_1","sourceRepos":["src_1"]},"instructions":[]}`
`Notes`: Permissions gate the call; invalid configs and name clashes stop replacement.

### `DELETE /api/v1/publications/{id}`
Removes a publication.

| Key parameters | Details |
| --- | --- |
| Path | `id` |
| Response | `204 No Content` |

`curl`: `curl -X DELETE -H 'Authorization: Bearer $TOKEN' https://api.doc.holiday/api/v1/publications/pub_1`
`JSON`: `{"id":"pub_1"}`
`Notes`: Permission checks apply; removal also clears linked instruction records and orphaned local instructions.

### `GET /api/v1/publications/{id}/health`
Reports whether a publication is misconfigured.

| Key parameters | Details |
| --- | --- |
| Path | `id` |
| Response | `200 OK` |

`curl`: `curl -H 'Authorization: Bearer $TOKEN' https://api.doc.holiday/api/v1/publications/pub_1/health`
`JSON`: `{"id":"pub_1"}`
`Notes`: The check can surface unhealthy docs or source connections and returns a message for the failure.

### `POST /api/v1/publications/{id}/sync`
Queues a sync run for the publication.

| Key parameters | Details |
| --- | --- |
| Path | `id` |
| Body | `wait` and `timeout` |
| Response | `202 Accepted` when queued |

`curl`: `curl -X POST https://api.doc.holiday/api/v1/publications/pub_1/sync -H 'Authorization: Bearer $TOKEN' -H 'Content-Type: application/json' -d '{"wait":true,"timeout":60000000000}'`
`JSON`: `{"wait":false,"timeout":60000000000}`
`Notes`: Permissions gate the call; `wait: true` blocks until completion or timeout.

## ModelsPublicationConfig

- `sourceRepos`: The source connections list for a publication.
- `docsRepo`: A publication must set this to its docs destination.
- `inputTriggers`: A map keyed by Connection ID, with events limited by connection type.
- `writeDocumentation`: Controls whether the publication writes documentation.
- `writeReleaseNotes`: Controls whether the publication writes release notes.
- `writeChangelogs`: Controls whether the publication writes changelogs.
- `styleGuide`: Nested per-type settings for documentation, release notes, and changelogs.
- `planningInstructions`: Text field used in publication configuration for planning guidance.
- `prCommitInstructions`: Text field used in publication configuration for pull request commit guidance.
- `notifierConnection`: The publication's notifier connection field.

## Behaviors

- Permission checks gate create, read, list, update, delete, health, and sync.
- Create and Update validate config before save and reject duplicate names.
- Health checks the docs destination and every source connection, then marks the publication unhealthy when any lookup fails.
- Sync queues a job, can wait for completion when requested, and returns accepted when queued.
- Delete removes the publication and cleans up linked instruction records.
