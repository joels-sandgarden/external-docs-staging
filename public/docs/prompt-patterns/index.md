# Prompt Patterns


Recipes for common documentation jobs: each pattern is a request skeleton you can copy, adapt, and send from [git](./f1-request-work-in-git.md) or [the app](./f2-request-work-in-the-app.md). The craft behind them is in [Writing requests](./p2-writing-requests.md).

## New page from scratch

When to use: a page that should exist and doesn't.

```
@doc.holiday, create a new file at /guides/webhook-setup.md

Write a how-to guide for setting up webhooks. Cover: creating the endpoint,
configuring the secret, and verifying delivery. The reader is an administrator
who has never used our webhooks. Explore the source to determine the actual
configuration fields and defaults — never assert a field you can't find.
End with a short "Verify it works" section.
```

Why it works: exact path, defined reader, bounded coverage, and an explicit *explore-to-determine* clause that trades completeness for accuracy.

## Update after a change

When to use: something shipped; a page is now wrong.

```
@doc.holiday update /docs/authentication.md to cover the token-refresh flow
merged in PR #198. Keep the API-key section unchanged. Update the code
examples to match the current parameter names in the source.
```

Why it works: names the trigger (the PR), the file, and the boundary. The best time to send it is in a comment **on that PR** — the context comes free.

## Release notes with a shape

When to use: you want release notes that read the way your team likes.

```
@doc.holiday write release notes covering everything merged since v2.3 at
/changelog/v2-4.md. Group by: New features, Improvements, Fixes. One line per
change, written for customers — describe what they can do now, not what we
refactored. Skip internal-only changes.
```

Why it works: range, grouping, altitude ("for customers"), and an exclusion rule — the four decisions release notes always need someone to make.

## The fix batch

When to use: review found several precise errors on one page. Batch them into one request; cite each error's location, the wrong text, and the right text.

```
@doc.holiday, update the file at /docs/quickstart.md

Apply exactly these corrections and change nothing else:
1. The page says the trial lasts "30 days" — it is 14 days.
2. In step 3, the button is labeled "Create project", not "New project".
3. Delete the sentence claiming exports run "hourly" — exports are on-demand only.
```

Why it works: "apply exactly / change nothing else" turns the writer into a surgeon. This is also the right way to *correct* Doc Holiday's own output — corrections through the same pipeline keep the page's history in one place.

## Building a doc set page by page

When to use: several related pages, written one request at a time.

Send one request per page, and paste the same short site map into each so every page cross-links to its siblings by their real paths — even the ones not written yet:

```
Site map (link to these paths, they are part of the same build):
/concepts.md — the shared vocabulary
/setup.md — installation and first run
/troubleshooting.md — common failures and fixes
```

Why it works: each page gets a fresh, focused run and its own review, while the shared map keeps the set coherent. One request per page also means one failure never blocks the batch.

## Placeholders that must survive

When to use: a human will insert something later — a screenshot, a metric, a date.

```
Where the dashboard image belongs, include this fenced block verbatim, exactly
as written — do not fill it in, describe it, or attempt to determine its value:

SCREENSHOT PLACEHOLDER: quickstart/dashboard.png
```

Why it works: without the "verbatim, do not attempt to determine" clause, a diligent writer will helpfully *fill in* the placeholder — with something plausible and wrong. Make non-negotiable tokens explicit.

## The review pass

When to use: you want to know what's wrong with a page before anything moves.

```
@doc.holiday review /docs/api-limits.md against the current source. List every
claim that no longer matches the code, with what the source actually says.
Propose no edits — report only.
```

Why it works: separating *finding* problems from *fixing* them gives you a reviewable list before anything moves — and pairs naturally with a fix batch as the follow-up.

## Next

The two standing levers that make every one of these patterns land better: [Writing style guides](./p3-writing-style-guides.md) and [Writing planning instructions](./p4-writing-planning-instructions.md).

