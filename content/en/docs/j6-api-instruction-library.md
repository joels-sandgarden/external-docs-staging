---
title: Instruction Library API
url: "docs/instruction-library-api"
description: "Manage Library instructions over the REST API."
---

This page covers direct integration with Doc Holiday's API.
Authentication, pagination, and general API conventions live in [j1-api-overview.md](./j1-api-overview.md).

## Instructions

Instructions store reusable text for a slot.

| Method | Path | Purpose | Key parameters | Example | Notable behaviors |
| --- | --- | --- | --- | --- | --- |
| GET | `/api/v1/instructions` | Lists instructions. | `type`, `global` | `curl -H "Authorization: Bearer $TOKEN" "https://api.doc.holiday/api/v1/instructions?type=documentation&global=true"`<br>`{"instructions":[{"id":"ins-0123456789abcdef"}]}` | Requires list permission. |
| GET | `/api/v1/instructions/{id}` | Returns one instruction. | `id` | `curl -H "Authorization: Bearer $TOKEN" "https://api.doc.holiday/api/v1/instructions/ins-0123456789abcdef"`<br>`{"id":"ins-0123456789abcdef"}` | Requires get permission; returns `404` when missing. |
| POST | `/api/v1/instructions` | Creates an instruction. | `name`, `type`, `content` | `curl -X POST -H "Authorization: Bearer $TOKEN" -H "Content-Type: application/json" "https://api.doc.holiday/api/v1/instructions" -d '{"name":"Docs tone","type":"documentation","content":"Write in short sentences."}'` | Requires create permission; rejects unknown types; returns `409` for duplicate name and type. Response is the full object, including `id`, `orgId`, `global`, `createdAt`, and `updatedAt`. |
| PUT | `/api/v1/instructions/{id}` | Replaces an instruction. | `id`, `name`, `type`, `content` | `curl -X PUT -H "Authorization: Bearer $TOKEN" -H "Content-Type: application/json" "https://api.doc.holiday/api/v1/instructions/ins-0123456789abcdef" -d '{"name":"Docs tone","type":"documentation","content":"Use short, direct sentences."}'` | Requires update permission; revalidates `type`; returns `409` for duplicate name and type. Response is the full object, including `id`, `orgId`, `global`, `createdAt`, and `updatedAt`. |
| DELETE | `/api/v1/instructions/{id}` | Deletes an instruction and its links. | `id` | `curl -X DELETE -H "Authorization: Bearer $TOKEN" "https://api.doc.holiday/api/v1/instructions/ins-0123456789abcdef"` | Requires delete permission; returns `204 No Content` with no response body, even when missing. |

## Instruction links

Instruction links attach an instruction to a publication slot. Slot types are `documentation`, `releaseNotes`, `changelog`, `commit`, `planning`, and `styleGuide`; `styleGuide` validates like the others but is not a publication slot. See [e2-instruction-slots-reference.md](./e2-instruction-slots-reference.md).

| Method | Path | Purpose | Key parameters | Example | Notable behaviors |
| --- | --- | --- | --- | --- | --- |
| POST | `/api/v1/instructions/{id}/links` | Creates one link. | `id`, `publicationId`, `slotType` | `curl -X POST -H "Authorization: Bearer $TOKEN" -H "Content-Type: application/json" "https://api.doc.holiday/api/v1/instructions/ins-0123456789abcdef/links" -d '{"publicationId":"pub-0123456789abcdef","slotType":"documentation"}'` | Requires create permission; validates `slotType`; duplicate instruction, publication, and slot combinations are accepted and appended at the next position. Response is the full object, including `id`, `orgId`, `position`, `createdAt`, and `updatedAt`. |
| GET | `/api/v1/instruction-links` | Lists links. | `instructionId`, `publicationId`, `slotType` | `curl -H "Authorization: Bearer $TOKEN" "https://api.doc.holiday/api/v1/instruction-links?publicationId=pub-0123456789abcdef&slotType=documentation"`<br>`{"instructionLinks":[{"id":"inl-0123456789abcdef"}]}` | Requires list permission; accepts any combination of filters. |
| GET | `/api/v1/instruction-links/{id}` | Returns one link. | `id` | `curl -H "Authorization: Bearer $TOKEN" "https://api.doc.holiday/api/v1/instruction-links/inl-0123456789abcdef"`<br>`{"id":"inl-0123456789abcdef"}` | Requires get permission; returns `404` when missing. |
| DELETE | `/api/v1/instruction-links/{id}` | Deletes one link. | `id` | `curl -X DELETE -H "Authorization: Bearer $TOKEN" "https://api.doc.holiday/api/v1/instruction-links/inl-0123456789abcdef"` | Requires delete permission; returns `204 No Content` with no response body, even when missing. |
| POST | `/api/v1/instructions/{id}/links/bulk` | Creates links across many publications and slots. | `id`, `publicationIds`, `slotTypes` | `curl -X POST -H "Authorization: Bearer $TOKEN" -H "Content-Type: application/json" "https://api.doc.holiday/api/v1/instructions/ins-0123456789abcdef/links/bulk" -d '{"publicationIds":["pub-0123456789abcdef","pub-fedcba9876543210"],"slotTypes":["documentation","planning"]}'` | Requires bulk create permission; validates every slot and publication; appends links instead of replacing them; returns `204 No Content` with no response body. |
| POST | `/api/v1/instruction-links/bulk-delete` | Deletes many links at once. | `ids` | `curl -X POST -H "Authorization: Bearer $TOKEN" -H "Content-Type: application/json" "https://api.doc.holiday/api/v1/instruction-links/bulk-delete" -d '{"ids":["inl-0123456789abcdef","inl-fedcba9876543210"]}'` | Requires bulk delete permission; skips missing IDs; returns `204 No Content` with no response body. |