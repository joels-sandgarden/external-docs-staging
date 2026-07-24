---
title: Trigger and Event Types
url: "docs/trigger-and-event-types"
description: "Every trigger and event type, enumerated."
---

This reference lists the trigger events Doc Holiday can react to and the Source types that support each one. See [Configure triggers](./d2-configure-triggers.md) and [Connection Types](./j8-connection-types.md).

| Event | Typical output | GitHub Repository | GitHub Repository (personal access token) | GitLab (multi-project access token) | GitLab Project | Bitbucket Repository (repository access token) | Bitbucket Project | Linear | Jira Read-Only | Jira Project |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Pull / Merge Requests | Page updates | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | — | — | — |
| New Issues | New pages or follow-up updates | ✓ | ✓ | ✓ | ✓ | — | — | ✓ | — | — |
| Issue Comments | Targeted updates | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | — | — |
| Releases | Release notes | ✓ | ✓ | ✓ | ✓ | — | — | — | — | — |
| Send to Doc | Page updates from a Jira issue | — | — | — | — | — | — | — | ✓ | ✓ |
| Issue status changes to | Workflow page updates | — | — | — | — | — | — | — | ✓ | ✓ |

Doc Holiday does not offer a scheduled trigger. For recurring cadence, use CI through [/g1-github-action.md](./g1-github-action.md).


---

<!-- doc-holiday-watermark -->
<p align="center">
  <a href="https://doc.holiday">
    <img alt="Doc Holiday logo" src="https://doc.holiday/assets/docs-by-doc-holiday.png" width="200">
  </a>
</p>
<p align="center">Docs authored by <a href="https://doc.holiday">Doc Holiday</a></p>
