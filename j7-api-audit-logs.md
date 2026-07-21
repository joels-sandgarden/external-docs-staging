# Audit log API reference
This page covers direct integration with Doc Holiday's API.

## List audit logs
`GET /api/v1/audit_logs`

Returns audit logs for the current organization.

| Parameter | Type | Behavior |
| --- | --- | --- |
| `type` | query | Matches one exact `AuditLogType` value. Omit it to exclude `assessment-*` logs. |
| `summary` | query | Matches text with `ILIKE`. |
| Pagination | shared | Uses the list pagination contract from [/j1-api-overview.md](/j1-api-overview.md). If `pageSize` is omitted, Doc Holiday uses the default page size. |

```bash
curl -H "Authorization: Bearer $TOKEN" \
  "https://api.doc.holiday/api/v1/audit_logs?summary=release"
```

```json
{
  "auditLogs": [
    {
      "id": "adl-00000000000000af",
      "orgId": "org-0000000000000001",
      "requestId": "req-0000000000000002",
      "userName": null,
      "type": "action-create",
      "summary": "A new publication called \"Docs\" was created",
      "delta": "with no public fields",
      "config": {},
      "adminUserName": null,
      "createdAt": "2026-07-21T12:00:00Z",
      "updatedAt": "2026-07-21T12:00:00Z"
    }
  ],
  "previousPageToken": "",
  "nextPageToken": "adl-00000000000000af"
}
```

Notes:
- Auth uses the standard SFS token flow described in [/j1-api-overview.md](/j1-api-overview.md).
- If list permission is unavailable, Doc Holiday limits results to permitted audit-log IDs.
- Unauthorized access remains the most common error when the caller cannot read the requested records.

## Get an audit log
`GET /api/v1/audit_logs/{id}`

Returns one audit log by ID.

| Parameter | Type | Behavior |
| --- | --- | --- |
| `id` | path | Use an `adl-` ID such as `adl-00000000000000af`. |

```bash
curl -H "Authorization: Bearer $TOKEN" \
  "https://api.doc.holiday/api/v1/audit_logs/adl-00000000000000af"
```

```json
{
  "id": "adl-00000000000000af",
  "orgId": "org-0000000000000001",
  "requestId": "req-0000000000000002",
  "userName": null,
  "type": "action-create",
  "summary": "A new publication called \"Docs\" was created",
  "delta": "with no public fields",
  "config": {},
  "adminUserName": null,
  "createdAt": "2026-07-21T12:00:00Z",
  "updatedAt": "2026-07-21T12:00:00Z"
}
```

Response body:

| Field | Type | Notes |
| --- | --- | --- |
| `id` | string | Audit log ID. |
| `orgId` | string | Organization ID. |
| `requestId` | string | Request ID. |
| `userName` | string or null | User name, when present. |
| `type` | string | One `AuditLogType` value. |
| `summary` | string | Short description of the event. |
| `delta` | string | Change summary. |
| `config` | object | Type-specific details. |
| `adminUserName` | string or null | Admin user name, when present. |
| `createdAt` | string | Creation timestamp. |
| `updatedAt` | string | UTC timestamp. |

Notes:
- Auth uses the standard SFS token flow described in [/j1-api-overview.md](/j1-api-overview.md).
- The API checks access to the specific audit log ID.
- Unauthorized access and invalid ID formats can block the request.

## Audit log types
- `error` — general error event.
- `assessment-pending` — assessment queued for review.
- `assessment-generate-release-notes` — assessment for release note generation.
- `assessment-edit-documentation` — assessment for documentation edits.
- `assessment-create-documentation` — assessment for new documentation.
- `assessment-general-updates` — assessment for general updates.
- `assessment-combine-pr` — assessment for combining a pull request.
- `assessment-github-operations` — assessment for GitHub operations.
- `action-create` — create action.
- `action-delete` — delete action.
- `action-update` — update action.
- `connection-sync` — connection sync event.
- `connection-health-check` — connection health check event.
- `publication-health-check` — publication health check event.