# Writing Planning Instructions


Planning instructions shape what Doc Holiday *decides to work on* before it writes a word: which pages should exist, what gets updated when something ships, and where the boundaries of the docs are. Style guides govern how prose reads; planning instructions govern coverage. They apply to every run for the [Publication](./d1-publications.md) — which is both their power and their hazard.

## Good uses

**Coverage rules** — the unit of documentation:

> Plan one page per user-facing feature area — never one page per API endpoint, never one page per code module.

**Boundaries** — what the docs deliberately ignore:

> Only document features visible in the dashboard or the public API. Ignore internal tooling, admin-only surfaces, and anything behind a feature flag.

**Site conventions** — where things go and what else must change:

> New guides go under /guides/. Whenever a page is added, add it to the sidebar file and the navigation index in the same piece of work.

**Update discipline** — what "react to a change" means:

> When a release changes existing behavior, update the affected pages rather than creating new ones. Create a new page only for a genuinely new capability.

## The overreach warning

Planning instructions apply to **every** run — including runs whose request asks for something else. A rule like:

> Only write to /content/release-notes.md.

…will make Doc Holiday redirect an explicit "update the install guide" request toward release notes, and report success. The rule did exactly what it said; it just said too much.

The discipline: keep planning instructions **structural** (units, boundaries, locations) and keep them **out of content decisions** (what any single page says). If a rule names a specific file as the only permitted output, or dictates what topic every run must produce, it will eventually fight a legitimate request — and the instruction wins.

## Worked examples

For a product-docs publication:

> - One page per feature area; cross-link between pages instead of repeating material.
> - Only document behavior visible to customers. Never document internal mechanisms.
> - New pages: /docs/. Update the sidebar in the same piece of work.
> - Never plan tutorial content — this publication is how-to and reference only.

For a from-scratch docs build driven one page at a time:

> - Plan only the page the request names; never add, split, or reorganize pages on your own.
> - The requested file path is exact and final.
> - Cross-link using the site map in the request, even to pages that don't exist yet.

That second set is how this documentation site was built — each page arrived as one request carrying its own brief, with planning instructions keeping every run inside its lane.

## Next

Pair with [Writing style guides](./p3-writing-style-guides.md) (the how-it-reads lever) and [Writing requests](./p2-writing-requests.md) (the per-run lever). How the levers compose: [Prompting guide](./p1-prompting-guide.md).

