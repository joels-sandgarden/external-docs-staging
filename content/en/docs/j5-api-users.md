---
title: Users API
url: "docs/users-api"
description: "Manage users over the REST API."
---

This page covers direct integration with Doc Holiday's API.

See [API overview](./j1-api-overview.md).

## GET /api/v1/me

Returns the authenticated user as `ModelsGetUserResponse`, the same shape used by `GET /api/v1/users/{id}`.

| Parameter | Notes |
| --- | --- |
| none | No query or path parameters. |

```bash
curl -H "Authorization: Bearer <token>" https://api.doc.holiday/api/v1/me
```

```json
{"id":"string","authId":"string","email":"string","name":"string","sfsToken":"","invitationAccepted":true,"orgId":"string","createdAt":"string","updatedAt":"string"}
```

Requires an `Authorization: Bearer <token>` header. Common errors: `400`, `500`.

## GET /api/v1/users

Returns `ModelsListUsersResponse` for users in the authenticated org, with `users`, `nextPageToken`, and `previousPageToken`.

| Parameter | Notes |
| --- | --- |
| email | Filter by email. |
| name | Filter by name. |
| authId | Filter by auth ID. |
| query | Free-text search. |
| roleIds | Filter by role IDs. |
| noBuiltinRole | Returns only users who have no builtin role. |
| invitationAccepted | Filter by invitation state. |
| shared pagination | Shared pagination fields from the API. |

```bash
curl -H "Authorization: Bearer <token>" "https://api.doc.holiday/api/v1/users?email=string"
```

```json
{"users":[{"id":"string","email":"string","name":"string"}],"nextPageToken":"string","previousPageToken":"string"}
```

Requires an `Authorization: Bearer <token>` header. Common errors: `400`, `500`.

## GET /api/v1/users/{id}

Returns one user in `ModelsGetUserResponse`.

| Parameter | Notes |
| --- | --- |
| id | Required path parameter. |

```bash
curl -H "Authorization: Bearer <token>" https://api.doc.holiday/api/v1/users/string
```

```json
{"id":"string","authId":"string","email":"string","name":"string","sfsToken":"","invitationAccepted":true,"orgId":"string","createdAt":"string","updatedAt":"string"}
```

Requires an `Authorization: Bearer <token>` header. Common errors: `400`, `500`.


---

<!-- doc-holiday-watermark -->
<p align="center">
  <a href="https://doc.holiday">
    <img alt="Doc Holiday logo" src="https://doc.holiday/assets/docs-by-doc-holiday.png" width="200">
  </a>
</p>
<p align="center">Docs authored by <a href="https://doc.holiday">Doc Holiday</a></p>
