# Connection types

This reference lists every supported Doc Holiday connection type, its role, parent requirement, and automatic trigger set. The table below stays a lookup register. It does not explain setup or workflow. It records the product model as it exists in the app.

Doc Holiday keeps the set closed. Each row pairs the Type label shown in the app with the API value used by the model. The Role column groups rows into provider, repository, context source, or notifier. The Requires column names a parent only when one exists. The Automatic triggers column lists exact trigger identifiers or `—`.

Provider rows sit above repository rows and other child rows. GitHub Application, GitLab Access Token, Bitbucket Workspace Access Token, Slack Application, and Atlassian Application serve as parent rows. GitHub also uses a personal access token path, which creates a direct repository row without a parent. GitLab and Bitbucket each split parent and project rows. Repository rows emit trigger events when the connected system supports them.

Context source rows usually stand alone. External Documentation, Notion, Google Drive, AWS (S3), Confluence, and Azure Blob Storage do not require parents. Linear is the only standalone context source with trigger support, and it exposes `newIssues` and `issueComments`. Jira Read-Only and Jira Project also belong to the context source family, and they add trigger support of their own.

Jira Project exposes `sendToDoc` and `issueStatusChange`. Atlassian Application serves as the parent row for Jira Project. Slack Application serves as the parent row for Slack Channel, and Slack Channel remains the only notifier connection. Atlassian Application and Slack Application stay as parent rows only.

The supported trigger identifiers are `pullRequests`, `newIssues`, `issueComments`, `releases`, `sendToDoc`, and `issueStatusChange`. Repository rows use the pull request, issue, comment, and release identifiers. Jira Project rows use the two Jira specific identifiers. Rows without event support show `—`.

The Role column groups families rather than platform features. A provider row does not emit events by itself. A repository row does. A context source row describes external content sources or issue tracking systems. A notifier row handles publication notifications only.

The table uses `—` deliberately. It marks rows with no parent and rows with no automatic events. That keeps the register narrow while still showing which entries participate in trigger handling and which entries only provide context or notification.

GitHub keeps both a parent app path and a direct token path. GitLab and Bitbucket use the same parent and child pattern. Atlassian Application follows that split for Jira Project.

Linear remains the only standalone context source with events, and Slack Channel remains the only notifier row.

| Type | API value | Role | Requires | Automatic triggers |
| --- | --- | --- | --- | --- |
| GitHub Application | `githubApp` | `provider` | — | — |
| GitLab Access Token | `gitlabProvider` | `provider` | — | — |
| Bitbucket Workspace Access Token | `bitbucketProvider` | `provider` | — | — |
| Slack Application | `slackApp` | `provider` | — | — |
| Atlassian Application | `atlassianForgeApp` | `provider` | — | — |
| GitHub Repository | `githubRepo` | `repository` | `GitHub Application` | `pullRequests`, `newIssues`, `issueComments`, `releases` |
| GitHub Repository (personal access token) | `githubAccessToken` | `repository` | — | `pullRequests`, `newIssues`, `issueComments`, `releases` |
| GitLab (multi-project access token) | `gitlab` | `repository` | — | `pullRequests`, `newIssues`, `issueComments`, `releases` |
| GitLab Project | `gitlabProject` | `repository` | `GitLab Access Token` | `pullRequests`, `newIssues`, `issueComments`, `releases` |
| Bitbucket Repository (repository access token) | `bitbucketRepo` | `repository` | — | `pullRequests`, `issueComments` |
| Bitbucket Project | `bitbucketProject` | `repository` | `Bitbucket Workspace Access Token` | `pullRequests`, `issueComments` |
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
5. Slack Channel is the only notifier connection.

## See also

[Sources](/c1-sources.md), [trigger and event types](/j9-trigger-and-event-types.md), and [API connections](/j3-api-connections.md).
