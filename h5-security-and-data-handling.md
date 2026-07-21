# Security and data handling

How Doc Holiday handles your code and your data — stated plainly.

## How Doc Holiday handles your code

Doc Holiday is SOC 2 Type II certified.

We do not retain any code in our systems. We read your code only while writing documentation, and only for writing documentation — through the [Sources](/c1-sources.md) you connect, using only the access you grant.

## Where inference runs

- On the **Bring Your Own Key** and **Open Source** plans, all writing runs on your own OpenAI key — requests go to OpenAI under your account. If your key is missing or rejected, work stops; Doc Holiday never falls back to anyone else's key.
- On the **Enterprise** plan, inference runs on model providers managed by the Doc Holiday team.

See [Billing and plans](/h4-billing-and-plans.md) for the plans themselves.

## What Doc Holiday never does

- **Write to your repositories without an approved pull request.** Drafts stay in Doc Holiday until a person approves them; everything lands as an ordinary PR your team merges.
- **Expose stored credentials.** Secrets are excluded from API responses and interface output by design, and credential-handling paths are built to keep keys out of logs.
- **React to unverified webhooks.** Inbound events from git providers are signature-verified before they are processed.

## Access control

Access is role-based — Reviewer, Writer, and Admin, in increasing order of capability ([User management](/h1-user-management.md)). API keys are created by admins, shown once, and expire ([API overview](/j1-api-overview.md)). Administrative actions and connection health changes are recorded in the [audit log](/h2-audit-log.md).

## Removing your data

Deleting a connection removes its stored secrets and, together with publication deletion, cleans up the knowledge derived from it. For complete removal of an organization and its data, contact the Doc Holiday team — full-organization deletion and purge are performed on request.

Questions this page doesn't answer are worth asking — reach us via [doc.holiday](https://doc.holiday/).
