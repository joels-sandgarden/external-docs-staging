This page covers direct integration with Doc Holiday's API.

Authentication, pagination, and general API conventions live in [j1-api-overview.md](/j1-api-overview.md).

## Instructions

Instructions store reusable text for a slot.

| Method | Path | Purpose | Key parameters | Example | Notable behaviors |
| --- | --- | --- | --- | --- | --- |
| GET | `/api/v1/instructions` | Lists instructions. | `type`, `global` | `curl -H "Authorization: Bearer $TOKEN" "$BASE_URL/api/v1/instructions?type=documentation&global=true"`<br>`{"items":[{"id":"ins_01"}]}` | Requires list permission. |
| GET | `/api/v1/instructions/{id}` | Returns one instruction. | `id` | `curl -H "Authorization: Bearer $TOKEN" "$BASE_URL/api/v1/instructions/ins_01"`<br>`{"id":"ins_01"}` | Requires get permission; returns `404` when missing. |
| POST | `/api/v1/instructions` | Creates an instruction. | `name`, `type`, `content` | `curl -X POST -H "Authorization: Bearer $TOKEN" -H "Content-Type: application/json" "$BASE_URL/api/v1/instructions" -d '{"name":"Docs tone","type":"documentation","content":"Write in short sentences."}'`<br>`{"name":"Docs tone","type":"documentation","content":"Write in short sentences."}` | Requires create permission; rejects unknown types; returns `409` for duplicate name and type. |
| PUT | `/api/v1/instructions/{id}` | Replaces an instruction. | `id`, `name`, `type`, `content` | `curl -X PUT -H "Authorization: Bearer $TOKEN" -H "Content-Type: application/json" "$BASE_URL/api/v1/instructions/ins_01" -d '{"name":"Docs tone","type":"documentation","content":"Use short, direct sentences."}'`<br>`{"name":"Docs tone","type":"documentation","content":"Use short, direct sentences."}` | Requires update permission; revalidates `type`; returns `409` for duplicate name and type. |
| DELETE | `/api/v1/instructions/{id}` | Deletes an instruction and its links. | `id` | `curl -X DELETE -H "Authorization: Bearer $TOKEN" "$BASE_URL/api/v1/instructions/ins_01"`<br>`{}` | Requires delete permission; returns `204` even when missing. |

## Instruction links

Instruction links attach an instruction to a publication slot. Slot types are `documentation`, `releaseNotes`, `changelog`, `commit`, `planning`, and `styleGuide`; `styleGuide` validates like the others but is not a publication slot. See [e2-instruction-slots-reference.md](/e2-instruction-slots-reference.md).

| Method | Path | Purpose | Key parameters | Example | Notable behaviors |
| --- | --- | --- | --- | --- | --- |
| POST | `/api/v1/instructions/{id}/links` | Creates one link. | `id`, `publicationId`, `slotType` | `curl -X POST -H "Authorization: Bearer $TOKEN" -H "Content-Type: application/json" "$BASE_URL/api/v1/instructions/ins_01/links" -d '{"publicationId":"pub_01","slotType":"documentation"}'` | Requires create permission; validates `slotType`; returns a conflict for duplicate instruction, publication, and slot. |
| GET | `/api/v1/instruction-links` | Lists links. | `instructionId`, `publicationId`, `slotType` | `curl -H "Authorization: Bearer $TOKEN" "$BASE_URL/api/v1/instruction-links?publicationId=pub_01&slotType=documentation"` | Requires list permission; accepts any combination of filters. |
| GET | `/api/v1/instruction-links/{id}` | Returns one link. | `id` | `curl -H "Authorization: Bearer $TOKEN" "$BASE_URL/api/v1/instruction-links/link_01"` | Requires get permission; returns `404` when missing. |
| DELETE | `/api/v1/instruction-links/{id}` | Deletes one link. | `id` | `curl -X DELETE -H "Authorization: Bearer $TOKEN" "$BASE_URL/api/v1/instruction-links/link_01"` | Requires delete permission; returns `204` even when missing. |
| POST | `/api/v1/instructions/{id}/links/bulk` | Creates links across many publications and slots. | `id`, `publicationIds`, `slotTypes` | `curl -X POST -H "Authorization: Bearer $TOKEN" -H "Content-Type: application/json" "$BASE_URL/api/v1/instructions/ins_01/links/bulk" -d '{"publicationIds":["pub_01","pub_02"],"slotTypes":["documentation","planning"]}'` | Requires bulk create permission; validates every slot and publication; appends links instead of replacing them. |
| POST | `/api/v1/instruction-links/bulk-delete` | Deletes many links at once. | `ids` | `curl -X POST -H "Authorization: Bearer $TOKEN" -H "Content-Type: application/json" "$BASE_URL/api/v1/instruction-links/bulk-delete" -d '{"ids":["link_01","link_02"]}'` | Requires bulk delete permission; skips missing IDs. |