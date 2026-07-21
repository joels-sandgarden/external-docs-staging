# API overview

This page covers direct integration with Doc Holiday's API.

## Overview

The public API exposes the contract for external systems that create and read `Connection`, `Conversation`, and related records. The generated OpenAPI spec defines the published surface, base URL, response statuses, and error schema. Only endpoints exposed in the public contract belong in this reference.

## Authentication and transport

- Base URL: `https://api.doc.holiday/api/v1`
- OpenAPI spec: `GET /api/v1/openapi.yaml`
- Create API keys in **Settings → API Keys**. That route is admin only.
- The create form sets `expiresAt` to 48 hours from creation by default. Change the expiration date to keep a key valid longer.
- The token appears only once after creation. Store it immediately.
- Send the key in `Authorization: Bearer <token>`.

## Naming and errors

Doc Holiday's API predates the rename from Automations to Publications. Current public endpoints use `/api/v1/publications/*`; `/api/v1/automations/*` remains as deprecated backward-compatible aliases.

API responses follow the OpenAPI contract:

- Success responses commonly use `200`, `201`, `202`, or `204`.
- Error responses return JSON in the form `{"error": "..."}`.
- Common failure statuses include `400`, `401`, and `500`.

## Permissions

An API key acts as the user who created it. That user's organization membership and role permissions determine what the key can access.

## Resource map

- [Publications](./j2-api-publications.md) — publication records and publication-scoped operations
- [Connections](./j3-api-connections.md) — connection records and connection-scoped operations
- [Work History](./j4-api-work-history.md) — conversations, turns, and comments
- [Users](./j5-api-users.md) — user identity and account data
- [Instruction Library](./j6-api-instruction-library.md) — instructions and instruction links
- [Audit Logs](./j7-api-audit-logs.md) — audit log records