# Writing requests

A request is the single biggest lever on what Doc Holiday produces for one piece of work. The same product, the same sources, and the same instructions can yield a mediocre page from a vague request and an excellent one from a precise request. This guide is the craft; where to type a request is covered in [Request work from git](/f1-request-work-in-git.md) and [Request work from the app](/f2-request-work-in-the-app.md).

## Name the outcome

Ask for the artifact you want to exist.

> **Weak:** `@doc.holiday look at the changes to the webhook code`
> **Strong:** `@doc.holiday write a troubleshooting section for webhook delivery failures and add it to /docs/integrations.md`

Doc Holiday decides how to explore; your job is to define what "done" looks like.

## Pin the path when you care where it lands

If the file matters, say it exactly. A request that names `/guides/sso.md` produces exactly that file; a request that says "document SSO somewhere sensible" makes Doc Holiday choose — and reviewing a choice costs more than making one.

> `@doc.holiday create a new file at /guides/sso.md covering the SAML setup added in v2.4`

## Scope both directions

Say what to cover **and** what to leave alone. Doc Holiday expands into adjacent territory when the boundary is unstated — usually helpfully, occasionally not.

> `@doc.holiday update /docs/install.md for the new Docker Compose flow. Don't change the Kubernetes section.`

## Ground it in real references

Anchor the request to things that exist: file paths, PR numbers, release tags, exact feature names. Every concrete reference removes a guess.

> `@doc.holiday write release notes covering PRs #212–#230, grouped by feature area, at /changelog/2026-07.md`

## Say how to spend uncertainty

Doc Holiday verifies what it writes against the source automatically — you never need to ask for that. What a request can still set is the default when the source runs out: for pages where a wrong claim is expensive — security notes, API behavior, migration guides — say `if something is uncertain, omit it rather than guess`. For pages where breadth matters more, say `expand freely where the source supports it`.

## Before and after

> **Weak:** `@doc.holiday the docs are out of date after the auth changes, can you fix them`
> **Strong:** `@doc.holiday update /docs/authentication.md to cover the token-refresh flow merged in PR #198. Keep the existing API-key section unchanged.`

The strong version names the file, the change that triggered the work, and the boundary — two sentences, and the review is usually a rubber stamp.

## Next

Durable preferences — voice, structure, coverage rules — don't belong in requests; put them in standing instructions so every run gets them. Start with [the Prompting guide](/p1-prompting-guide.md), then [Writing style guides](/p3-writing-style-guides.md). For ready-made request skeletons, see [Prompt patterns](/p5-prompt-patterns.md).
