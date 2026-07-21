This page covers direct integration with Doc Holiday's API.

Authentication, pagination, and general API conventions live in [j1-api-overview.md](/j1-api-overview.md).

## Instructions

The Instructions resource stores reusable text for a slot. The API accepts the instruction type enum. `styleGuide` validates like the others, but it is not a publication slot. For slot meaning, see [e2-instruction-slots-reference.md](/e2-instruction-slots-reference.md).

### GET /api/v1/instructions
Retrieves instructions. Query by `type` or `global`.

| Param | In | Type | Notes |
| --- | --- | --- | --- |
| `type` | query | string | Optional instruction type |
| `global` | query | boolean | Optional global filter |

```sh
curl -H "Authorization: Bearer $TOKEN" "$BASE_URL/api/v1/instructions?type=documentation&global=true"
```

```json
[
  {
    "id": "ins_01",
    "name": "Docs tone",
    "type": "documentation",
    "content": "Write in short sentences.",
    "global": true
  }
]
```

Behaviors: Requires list permission. Returns `200`.

### GET /api/v1/instructions/{id}
Retrieves one instruction.

| Param | In | Type | Notes |
| --- | --- | --- | --- |
| `id` | path | string | Instruction ID |

```sh
curl -H "Authorization: Bearer $TOKEN" "$BASE_URL/api/v1/instructions/ins_01"
```

```json
{
  "id": "ins_01",
  "name": "Docs tone",
  "type": "documentation",
  "content": "Write in short sentences.",
  "global": true
}
```

Behaviors: Requires get permission. Returns `404` when the ID is missing.

### POST /api/v1/instructions
Creates one instruction.

| Param | In | Type | Notes |
| --- | --- | --- | --- |
| `name` | body | string | Required |
| `type` | body | string | Required instruction type |
| `content` | body | string | Required instruction text |

```sh
curl -X POST -H "Authorization: Bearer $TOKEN" -H "Content-Type: application/json" "$BASE_URL/api/v1/instructions" -d '{"name":"Docs tone","type":"documentation","content":"Write in short sentences."}'
```

```json
{
  "name": "Docs tone",
  "type": "documentation",
  "content": "Write in short sentences."
}
```

Behaviors: Requires create permission. Rejects unknown types. Returns `409` when the same name and type already exist. Returns `201`.

### PUT /api/v1/instructions/{id}
Replaces one instruction.

| Param | In | Type | Notes |
| --- | --- | --- | --- |
| `id` | path | string | Instruction ID |
| `name` | body | string | Required |
| `type` | body | string | Required instruction type |
| `content` | body | string | Required instruction text |

```sh
curl -X PUT -H "Authorization: Bearer $TOKEN" -H "Content-Type: application/json" "$BASE_URL/api/v1/instructions/ins_01" -d '{"name":"Docs tone","type":"documentation","content":"Use short, direct sentences."}'
```

```json
{
  "id": "ins_01",
  "name": "Docs tone",
  "type": "documentation",
  "content": "Use short, direct sentences."
}
```

Behaviors: Requires update permission. Revalidates `type`. Replaces all fields. Returns `409` when the same name and type already exist. Returns `200`.

### DELETE /api/v1/instructions/{id}
Deletes one instruction and its links.

| Param | In | Type | Notes |
| --- | --- | --- | --- |
| `id` | path | string | Instruction ID |

```sh
curl -X DELETE -H "Authorization: Bearer $TOKEN" "$BASE_URL/api/v1/instructions/ins_01"
```

```json
{}
```

Behaviors: Requires delete permission. Returns `204`, even when the ID is missing.

## Instruction links

Instruction links attach one instruction to one publication slot. The resolver joins live links with blank lines and falls back to the publication's inline text when no live links exist or the library feature is off.

See the slot table below for the enum values and the slot reference page.

| Slot type | Notes |
| --- | --- |
| `documentation` | Documentation slot |
| `releaseNotes` | Release notes slot |
| `changelog` | Changelog slot |
| `commit` | Commit instruction slot |
| `planning` | Planning instruction slot |
| `styleGuide` | Valid enum value; not a publication slot |

### POST /api/v1/instructions/{id}/links
Creates one link.

| Param | In | Type | Notes |
| --- | --- | --- | --- |
| `id` | path | string | Instruction ID |
| `publicationId` | body | string | Publication ID |
| `slotType` | body | string | One of the slot types above |

```sh
curl -X POST -H "Authorization: Bearer $TOKEN" -H "Content-Type: application/json" "$BASE_URL/api/v1/instructions/ins_01/links" -d '{"publicationId":"pub_01","slotType":"documentation"}'
```

```json
{
  "instructionId": "ins_01",
  "publicationId": "pub_01",
  "slotType": "documentation"
}
```

Behaviors: Requires create permission. Validates `slotType`. Returns a conflict error when the same instruction, publication, and slot already exist.

### GET /api/v1/instruction-links
Lists links.

| Param | In | Type | Notes |
| --- | --- | --- | --- |
| `instructionId` | query | string | Optional filter |
| `publicationId` | query | string | Optional filter |
| `slotType` | query | string | Optional filter |

```sh
curl -H "Authorization: Bearer $TOKEN" "$BASE_URL/api/v1/instruction-links?publicationId=pub_01&slotType=documentation"
```

```json
[
  {
    "id": "link_01",
    "instructionId": "ins_01",
    "publicationId": "pub_01",
    "slotType": "documentation"
  }
]
```

Behaviors: Requires list permission. Supports any combination of the three filters.

### GET /api/v1/instruction-links/{id}
Retrieves one link.

| Param | In | Type | Notes |
| --- | --- | --- | --- |
| `id` | path | string | Link ID |

```sh
curl -H "Authorization: Bearer $TOKEN" "$BASE_URL/api/v1/instruction-links/link_01"
```

```json
{
  "id": "link_01",
  "instructionId": "ins_01",
  "publicationId": "pub_01",
  "slotType": "documentation"
}
```

Behaviors: Requires get permission. Returns `404` when the ID is missing.

### DELETE /api/v1/instruction-links/{id}
Deletes one link.

| Param | In | Type | Notes |
| --- | --- | --- | --- |
| `id` | path | string | Link ID |

```sh
curl -X DELETE -H "Authorization: Bearer $TOKEN" "$BASE_URL/api/v1/instruction-links/link_01"
```

```json
{}
```

Behaviors: Requires delete permission. Returns `204`, even when the ID is missing.

### POST /api/v1/instructions/{id}/links/bulk
Creates links for one instruction across many publications and slots.

| Param | In | Type | Notes |
| --- | --- | --- | --- |
| `id` | path | string | Instruction ID |
| `publicationIds` | body | array[string] | Required |
| `slotTypes` | body | array[string] | Required |

```sh
curl -X POST -H "Authorization: Bearer $TOKEN" -H "Content-Type: application/json" "$BASE_URL/api/v1/instructions/ins_01/links/bulk" -d '{"publicationIds":["pub_01","pub_02"],"slotTypes":["documentation","planning"]}'
```

```json
{
  "publicationIds": ["pub_01", "pub_02"],
  "slotTypes": ["documentation", "planning"]
}
```

Behaviors: Requires bulk create permission. Validates every slot type. Checks the instruction and each publication before linking. Appends links instead of replacing existing ones.

### POST /api/v1/instruction-links/bulk-delete
Deletes many links at once.

| Param | In | Type | Notes |
| --- | --- | --- | --- |
| `ids` | body | array[string] | Link IDs |

```sh
curl -X POST -H "Authorization: Bearer $TOKEN" -H "Content-Type: application/json" "$BASE_URL/api/v1/instruction-links/bulk-delete" -d '{"ids":["link_01","link_02"]}'
```

```json
{
  "ids": ["link_01", "link_02"]
}
```

Behaviors: Requires bulk delete permission. When bulk delete permission is missing, the API checks each ID individually. Missing IDs are skipped.