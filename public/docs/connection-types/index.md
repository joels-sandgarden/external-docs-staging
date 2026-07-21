# Connection Types


This reference lists every supported Doc Holiday connection type, its role, parent requirement, and automatic trigger set. The table below stays a lookup register. It does not explain setup or workflow. It records the product model as it exists in the app.

Doc Holiday keeps the set closed. Each row pairs the Type label shown in the app with the API value used by the model. The Role column groups rows into git provider, git repository, context source, or notifier. The Requires column names a parent only when one exists. The Automatic triggers column lists exact trigger identifiers or `—`.

Git provider rows sit above repository rows. GitHub App, GitLab provider, and Bitbucket provider serve as parent rows. GitHub also uses a personal access token path, which creates a direct repository row without a parent. GitLab and Bitbucket each split provider and project rows. Repository rows are the direct or provider-backed source connections that emit trigger events.

Context source rows usually stand alone. Documentation, Notion, Google Drive, AWS, Confluence, and Azure Blob do not require parents. Linear is the only standalone context source with trigger support, and it exposes `newIssues` and `issueComments`. Jira project and Atlassian Forge Jira project also belong to the context source family, but they add trigger support of their own.

Jira project and Atlassian Forge Jira project expose `sendToDoc` and `issueStatusChange`. Atlassian Forge App serves as the parent row for Atlassian Forge Jira project. Slack App serves as the parent row for Slack Channel, and Slack Channel remains the only notifier connection. Slack App and Atlassian Forge App stay as parent rows only.

The supported trigger identifiers are `pullRequests`, `newIssues`, `issueComments`, `releases`, `sendToDoc`, and `issueStatusChange`. Repository rows use the pull request, issue, comment, and release identifiers. Jira project rows and Atlassian Forge Jira project rows use the two Jira-specific identifiers. Rows without event support show `—`.

The Role column groups families rather than platform features. A git provider row does not emit events by itself. A git repository row does. A context source row describes external content sources or issue-tracking systems. A notifier row handles publication notifications only.

The table uses `—` deliberately. It marks rows with no parent and rows with no automatic events. That keeps the register narrow while still showing which entries participate in trigger handling and which entries only provide context or notification.

Atlassian Forge follows the same split as GitLab and Bitbucket. One row names the app parent, and the other row names the Jira project source. The parent row stays triggerless, and the project row carries the event set.

The table keeps parent-only rows near the top, event-bearing rows in the middle, and the notifier row at the end. That order matches the way the product model groups families.

GitHub keeps both a parent app path and a direct token path. That gives the family one parent-backed repository row and one direct repository row.

GitLab and Bitbucket use the same provider-and-project pattern. The provider rows stay parent only, and the project rows carry the trigger set. Atlassian Forge uses the same pattern across its app and Jira project rows.

Linear stays the only standalone context source that emits events. Jira project and Atlassian Forge Jira project carry `sendToDoc` and `issueStatusChange`. Slack Channel remains the only notifier row.

| Type | API value | Role | Requires | Automatic triggers |
| --- | --- | --- | --- | --- |
| GitHub Application | `githubApp` | `git provider` | — | — |
| GitLab Access Token | `gitlabProvider` | `git provider` | — | — |
| Bitbucket Workspace Access Token | `bitbucketProvider` | `git provider` | — | — |
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
