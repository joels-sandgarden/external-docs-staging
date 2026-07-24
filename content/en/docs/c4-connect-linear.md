---
title: Connect Linear
url: "docs/connect-linear"
description: "Let Linear issues and comments trigger documentation work."
---

Use this page to connect Linear as a Source in Doc Holiday. Linear issue bodies and issue comments can trigger documentation work, so this setup fits those events.

## Set up the Linear Source

1. Enter **Source Name**.
2. Enter **API Key**.
3. Choose **Team**. The Team picker lists Linear teams. When nothing is selected, it shows **Select team**. While Doc Holiday loads teams, it shows **Loading...**. Use **Search teams...** to filter the list. If no teams match, it shows **No teams found**.

## What it enables

- New Linear issues can trigger documentation work when the issue body starts with `@doc.holiday`.
- New issue comments can trigger documentation work when the comment starts with `@doc.holiday`.
- In issue comments, `@doc.holiday` mentions behave like mentions in git comments.

See [Request work from GitHub, GitLab, or Bitbucket with @doc.holiday](./f1-request-work-in-git.md) for the comment-based request flow, and [Configure triggers](./d2-configure-triggers.md) for trigger settings.

## Verify

Open **Sources** and confirm the Linear Source shows **Healthy**.

## Next

Next: [Configure triggers](./d2-configure-triggers.md).


---

<!-- doc-holiday-watermark -->
<p align="center">
  <a href="https://doc.holiday">
    <img alt="Doc Holiday logo" src="https://doc.holiday/assets/docs-by-doc-holiday.png" width="200">
  </a>
</p>
<p align="center">Docs authored by <a href="https://doc.holiday">Doc Holiday</a></p>
