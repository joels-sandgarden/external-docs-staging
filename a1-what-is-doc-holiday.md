# What is Doc Holiday?

Code changes constantly; documentation is updated occasionally, by hand, when someone remembers. The gap between what your product now does and what's written down — documentation drift — widens with every release, and closing it manually is the tedious 80% of a documentation job that nobody wants.

Doc Holiday closes that gap continuously. It writes and maintains documentation and release notes from what actually shipped: it reads your real source — code, commits, pull requests, and the context around them — and produces docs that are reconciled against the source every time something ships.

## How people use it

**An engineer, without leaving the pull request.** Comment `@doc.holiday update the authentication guide to cover the new token flow` on a PR, and Doc Holiday replies on the thread with a documentation pull request ready for review.

**A product manager or support engineer, from the app.** Type a plain-language request into [app.doc.holiday](https://app.doc.holiday) — "write release notes covering everything merged since v2.3" — and review the draft file by file when it's ready.

**Fully automated, as part of shipping.** Configure a [Publication](/d1-publications.md) to react to merged pull requests or releases, and the affected pages get reconciled and the release notes written without anyone having to ask — with your team still approving every change. The set-it-once configuration, full prompts included: [Fully automated setup](/p6-fully-automated-setup.md).

## What makes it different

- **It writes from the source.** Every page is grounded in the actual repository state at the time of writing — Doc Holiday explores the code and its history first, and writes only what it finds there.
- **Humans stay in the loop.** Doc Holiday drafts; people review. Work is staged as reviewable diffs, commented on, revised, and only then merged as a normal pull request into your docs repo. It behaves like a diligent teammate opening PRs.
- **It keeps the docs current, release after release.** The first draft is the easy part. The value is the ongoing loop: something ships, the affected pages get reconciled, the release notes get written.
- **It fits the tools you already use.** GitHub, GitLab, and Bitbucket; docs sites in ordinary git repos; CI pipelines; Slack; and the context systems around your code — Notion, Confluence, Jira, Linear, Google Drive.

And one more thing: **this site is the proof.** The documentation you're reading is written and maintained by Doc Holiday itself.

## Where to go next

- **[Quickstart](/b1-quickstart.md)** — from sign-up to your first merged, Doc-Holiday-written doc.
- **[How Doc Holiday works](/a2-how-doc-holiday-works.md)** — what happens between your request and the PR.
- **[Concepts](/a3-concepts.md)** — the vocabulary: Publications, Sources, the Library, Work History.
