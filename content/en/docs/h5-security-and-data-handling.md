---
title: Security and Data Handling
url: "docs/security-and-data-handling"
description: "What Doc Holiday reads, stores, and never does with your code."
---

What Doc Holiday reads, what it stores, and what happens to your data — stated plainly.

## What Doc Holiday reads

Doc Holiday reads the [Sources](./c1-sources.md) you connect: the repositories a [Publication](./d1-publications.md) watches and writes to, and any context systems you add. It re-reads connected sources regularly — roughly every couple of hours per connection — and reads the current source again as part of doing work. It reads only through the access you grant, and an unhealthy connection stops being read until it's fixed.

## What Doc Holiday stores

**Derived knowledge, not a copy of your repository.** To write well without re-deriving everything on every run, Doc Holiday keeps summaries and structured notes about your connected sources, together with reference pointers back to where each fact came from. Long-term knowledge about your code is stored in this derived form; when a connection or publication is removed, the knowledge derived from it is cleaned up.

**Your work record.** Requests, plans, proposed changes (including the before-and-after content of edited files), comments, and revision history are stored in Doc Holiday's database as the [Work History](./f4-work-history.md) record — that's what makes review, revision, and an audit trail possible. Approved content additionally becomes ordinary commits in your own docs repository, which remains the home of your published documentation.

**Connection credentials, encrypted.** Tokens, keys, and passwords in connection configurations are encrypted at rest using envelope encryption backed by a cloud key-management service, with each secret cryptographically bound to its own connection. Deleting a connection scrubs its stored secrets. The same scheme protects [AI provider keys](./h3-ai-provider-keys.md), which are also only ever returned in truncated form after creation.

**Model traffic, briefly.** Doc Holiday keeps an internal log of model requests for reliability and support. The request and response content in that log is scrubbed after four days; only non-content metadata (model, token counts, timing, error states) is retained beyond that.

## Where inference runs

- On the **Bring Your Own Key** and **Open Source** plans, all writing runs on your own OpenAI key — requests go to OpenAI under your account. If your key is missing or rejected, work stops; Doc Holiday never falls back to anyone else's key.
- On the **Enterprise** plan, inference runs on model providers managed by the Doc Holiday team.

See [Billing and plans](./h4-billing-and-plans.md) for the plans themselves.

## What Doc Holiday never does

- **Write to your repositories without an approved pull request.** Drafts stay in Doc Holiday until a person approves them; everything lands as an ordinary PR your team merges.
- **Expose stored credentials.** Secrets are excluded from API responses and interface output by design, and credential-handling paths are built to keep keys out of logs.
- **React to unverified webhooks.** Inbound events from git providers are signature-verified before they are processed.

## Access control

Access is role-based — Reviewer, Writer, and Admin, in increasing order of capability ([User management](./h1-user-management.md)). API keys are created by admins, shown once, and expire ([API overview](./j1-api-overview.md)). Administrative actions and connection health changes are recorded in the [audit log](./h2-audit-log.md).

## Removing your data

Deleting a connection removes its stored secrets and, together with publication deletion, cleans up the knowledge derived from it. For complete removal of an organization and its data, contact the Doc Holiday team — full-organization deletion and purge are performed on request.

Questions this page doesn't answer are worth asking — reach us via [doc.holiday](https://doc.holiday/).
