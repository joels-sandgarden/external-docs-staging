# How this site is made

Short answer: by the product it documents.

This site is a Doc Holiday [Publication](/d1-publications.md). Its [Sources](/c1-sources.md) are Doc Holiday's own source code; its docs destination is the git repository this site is served from. Every documentation page here was written by Doc Holiday, one request per page, the same way a customer's docs are written.

## The loop, applied to ourselves

Each page begins as a written request: the file path, what the page must answer, and which parts of the product it covers. Doc Holiday explores the connected source, drafts the page as a set of reviewable changes, and stages the work in [Work History](/f4-work-history.md).

Then the human part — the same review gate we recommend to every customer:

1. **Fact-check.** Every claim on the drafted page — every screen label, status name, configuration field — is verified against the product source before the work is approved. Pages that fail are corrected the same way they were written: by sending Doc Holiday the exact corrections as a new request, never by hand-editing the output.
2. **Approve.** Approved work becomes an ordinary pull request against this site's repository, and merging it publishes the page.
3. **Maintain.** When Doc Holiday's own code changes, the affected pages are reconciled the same way — which is the product's entire point.

## What the humans do

People still review every page, take the screenshots, decide the site's structure, and write this meta page you're reading. Doc Holiday does the part that doesn't scale: reading the source and keeping the words true to it.

[REVIEW_PROCESS_NOTE]

## The honest pitch

If you're evaluating Doc Holiday, this site is a fair specimen of its output on a real codebase — including the review process around it. The same loop — request, draft, review, merge — is what it runs on your repositories.

Start with [What is Doc Holiday](/a1-what-is-doc-holiday.md), or go straight to the [Quickstart](/b1-quickstart.md).
