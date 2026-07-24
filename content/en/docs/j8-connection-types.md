---
title: Connection Types
url: "docs/connection-types"
description: "Reference: every connection type, its role, and its triggers."
---

This reference lists every supported Doc Holiday connection type, its role, parent requirement, and automatic trigger set. The table below stays a lookup register, not a setup guide. It records the closed set that appears in the app.

Doc Holiday keeps the set closed. Each row pairs the Type label shown in the app with the API value used by the model. The Role column groups rows into provider, git repository, context source, or notifier. The Requires column names a parent only when one exists. The Automatic triggers column lists exact trigger identifiers or `—`.

GitHub, GitLab, and Bitbucket each split parent and direct access rows. GitHub also uses a personal access token path. GitLab also uses a multi-project access token path. Bitbucket also uses a repository access token path. Repository rows are the direct or provider-backed source connections that emit trigger events.

Context source rows usually stand alone. External Documentation, Notion, Google Drive, AWS, Confluence, and Azure Blob Storage do not require parents. Linear is the only standalone context source with trigger support, and it exposes `newIssues` and `issueComments`. Jira Read-Only and Jira Project also belong to the context source family, and both use the Jira specific identifiers.

Jira Read-Only and Jira Project expose `sendToDoc` and `issueStatusChange`. Jira Read-Only stands alone. Atlassian Application serves as the parent row for Jira Project. Slack Application serves as the parent row for Slack Channel, and Slack Channel remains the only notifier connection.

The supported trigger identifiers are `pullRequests`, `newIssues`, `issueComments`, `releases`, `sendToDoc`, and `issueStatusChange`. Repository rows use the pull request, issue, comment, and release identifiers. Jira Read-Only and Jira Project rows use the two Jira specific identifiers. Rows without event support show `—`.

The Role column groups families rather than platform features. A provider row does not emit events by itself. A git repository row does. A context source row describes external content sources or issue-tracking systems. A notifier row handles publication notifications only.

The table uses `—` deliberately. It marks rows with no parent and rows with no automatic events. That keeps the register narrow while still showing which entries participate in trigger handling and which entries only provide context or notification.

GitHub, GitLab, Bitbucket, Slack, and Atlassian Application rows stay grouped by family so the parent rows remain easy to scan before the child rows.

The table keeps parent-only rows near the top, event-bearing rows in the middle, and the notifier row at the end. That order matches the way the product model groups families.

GitHub keeps both a parent app path and a direct token path. That gives the family one parent-backed repository row and one direct repository row.

GitLab and Bitbucket use the same provider-and-project pattern. The provider rows stay parent only, and the project rows carry the trigger set. Atlassian Application uses the same pattern across its app and Jira project rows.

Linear stays the only standalone context source that emits events. Jira Read-Only and Jira Project carry `sendToDoc` and `issueStatusChange`. Slack Channel remains the only notifier row.

| Type | API value | Role | Requires | Automatic triggers |
| --- | --- | --- | --- | --- |
| GitHub Application | `githubApp` | `provider` | — | — |
| GitLab Access Token | `gitlabProvider` | `provider` | — | — |
| Bitbucket Workspace Access Token | `bitbucketProvider` | `provider` | — | — |
| Slack Application | `slackApp` | `provider` | — | — |
| Atlassian Application | `atlassianForgeApp` | `provider` | — | — |
| GitHub Repository | `githubRepo` | `git repository` | `GitHub Application` | `pullRequests`, `newIssues`, `issueComments`, `releases` |
| GitHub Repository (personal access token) | `githubAccessToken` | `git repository` | — | `pullRequests`, `newIssues`, `issueComments`, `releases` |
| GitLab (multi-project access token) | `gitlab` | `git repository` | — | `pullRequests`, `newIssues`, `issueComments`, `releases` |
| GitLab Project | `gitlabProject` | `git repository` | `GitLab Access Token` | `pullRequests`, `newIssues`, `issueComments`, `releases` |
| Bitbucket Repository (repository access token) | `bitbucketRepo` | `git repository` | — | `pullRequests`, `issueComments` |
| Bitbucket Project | `bitbucketProject` | `git repository` | `Bitbucket Workspace Access Token` | `pullRequests`, `issueComments` |
| External Documentation | `documentation` | `context source` | — | — |
| Notion | `notion` | `context source` | — | — |
| Google Drive | `gcp` | `context source` | — | — |
| AWS (S3) | `aws` | `context source` | — | — |
| Linear | `linear` | `context source` | — | `newIssues`, `issueComments` |
| Confluence | `confluence` | `context source` | — | — |
| Jira Read-Only | `jiraProject` | `context source` | — | `sendToDoc`, `issueStatusChange` |
| Azure Blob Storage | `azureBlob` | `context source` | — | — |
| Jira Project | `atlassianForgeJiraProject` | `context source` | `Atlassian Application` | `sendToDoc`, `issueStatusChange` |
| Slack Channel | `slackChannel` | `notifier` | `Slack Application` | — |

## Footnotes

1. GitHub Repository ↔ GitHub Repository (personal access token)
2. GitLab Project ↔ GitLab (multi-project access token)
3. Bitbucket Project ↔ Bitbucket Repository (repository access token)
4. `gcp` appears in the UI as Google Drive.
5. Slack Channel is the only Publication notifier.

## See also

[Sources](./c1-sources.md), [trigger and event types](./j9-trigger-and-event-types.md), and [API connections](./j3-api-connections.md).


---

<!-- doc-holiday-watermark -->
<p align="center">
  <a href="https://doc.holiday">
    <img alt="Doc Holiday logo" src="https://doc.holiday/assets/docs-by-doc-holiday.png" width="200">
  </a>
</p>
<p align="center">Docs authored by <a href="https://doc.holiday">Doc Holiday</a></p>
