---
title: Troubleshooting and FAQ
url: "docs/troubleshooting-and-faq"
description: "Symptom-first answers to the problems that actually come up."
---

Symptom-first answers to the problems that actually come up. Each section: what's happening, how to fix it, and how to avoid it next time.

## I mentioned @doc.holiday and nothing happened

The mention must come at the **start** of the comment — `@doc.holiday, update the install guide` works; a mention buried mid-paragraph doesn't. If the mention was first and there's still no 👀 reaction, check three things in order:

1. The repository is connected as a Source and its connection is **Healthy** ([manage connections](./c7-manage-connections.md)).
2. A [Publication](./d1-publications.md) includes that repository among its Sources.
3. You have write access to that Publication.

If all three hold and there's still no entry in [Work History](./f4-work-history.md), the request never reached Doc Holiday — re-check the connection's health and try once more.

## My connection shows Unhealthy

The credentials or access behind the connection stopped working — a revoked token, an uninstalled app, a repository that moved. Doc Holiday stops re-reading an unhealthy source until it's fixed, so its information goes stale (existing docs are unaffected).

Open the connection, update the credentials or reinstall the provider application, and confirm the badge returns to **Healthy**. Details per provider: [Connect GitHub](./b2-connect-github.md), [GitLab](./b3-connect-gitlab.md), [Bitbucket](./b4-connect-bitbucket.md).

## An entry says Needs Attention

Needs Attention means Doc Holiday is asking *you* something. Open the entry's **Messages** tab, read the question, and reply. Your reply starts a new pass and the work continues.

## The draft touched files I didn't want

Two remedies, in order of immediacy:

- **Now:** in the entry's **Files** tab, exclude the files you don't want before approving — excluded files stay out of the pull request.
- **Next time:** scope the request in both directions ("update X; don't change Y"). See [Writing requests](./p2-writing-requests.md).

## A request errored

Open the entry and retry the failed pass. If it fails again on a Bring Your Own Key or Open Source plan, check [AI provider keys](./h3-ai-provider-keys.md): a rejected or removed key stops all writing work, and on the Bring Your Own Key plan a lapsed subscription does the same ([Billing and plans](./h4-billing-and-plans.md)). Doc Holiday never falls back to someone else's key.

## The docs pull request has merge conflicts

Doc Holiday's PRs are ordinary git PRs, and they age like anyone else's. If the docs repo moved on and the PR conflicts, close it and send the request again — a fresh run drafts against the current state of the repo, which is usually faster than resolving conflicts by hand.

## It wrote about the wrong thing

The request was probably broader than it felt when you typed it. The fix is steering: name the outcome, pin the file path, and set boundaries — the [Prompting guide](./p1-prompting-guide.md) is the five-minute version, and durable preferences belong in [style guides](./p3-writing-style-guides.md) rather than repeated in every request.

## It keeps making the same stylistic mistake

Add the rule that would have prevented it to your style-guide instruction — one checkable rule per recurring miss ([Writing style guides](./p3-writing-style-guides.md)). Corrections sent as requests fix one page; rules fix every future page.

## FAQ

**Who can see my code?** Doc Holiday reads the sources you connect and stores what it needs to write well; drafts stay in Doc Holiday until you approve them. The full story: [Security and data handling](./h5-security-and-data-handling.md).

**Can I run it on a schedule?** There's no built-in scheduler — use [triggers](./d2-configure-triggers.md) to react to merges and releases, or the [GitHub Action](./g1-github-action.md) from a scheduled CI workflow.

**Which git providers are supported?** GitHub, GitLab, and Bitbucket — see [Getting started](./b1-quickstart.md).

**Does someone have to review every change?** Yes, by design. Work stages for review and becomes a pull request only when a person approves it ([Review and revise](./f3-review-and-revise.md)).
