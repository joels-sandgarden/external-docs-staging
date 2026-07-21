# Connection types

This reference lists every supported Doc Holiday connection type, its role, parent requirements, and automatic triggers.

Doc Holiday treats connection types as a closed set. Git provider rows sit above repository rows, and the repository rows are the triggerable connections for pull request, issue, and release events. Context source rows cover documentation systems and other external content sources. Slack Channel is the only notifier connection, and Slack App and Atlassian Forge App are the parent rows that support other connections.

GitHub, GitLab, and Bitbucket each appear as a provider row plus one or more repository rows. Provider rows are the parent layer. Repository rows are the direct or provider-backed source connections that can emit pull request, issue, and release events.

Documentation, Notion, Google Drive, AWS, Confluence, and Azure Blob are standalone context sources. Linear is the standalone context source with issue events. Jira project and Atlassian Forge Jira project are the issue-tracking rows with send-to-doc and issue-status-change events. Slack App and Atlassian Forge App are parent rows only; Slack Channel is the notifier row and depends on Slack App.

The Type column uses the user-facing label shown in the app. The API value column keeps the wire identifier from the connection model. The Requires column shows the parent connection only when the source config points to one; otherwise it is `—`. The Automatic triggers column shows the exact event identifiers used by Doc Holiday, or `—` when a connection type does not emit events. Rows without a parent or trigger use `—` to keep the register compact.

The supported trigger event identifiers are `pullRequests`, `newIssues`, `issueComments`, `releases`, `sendToDoc`, and `issueStatusChange`. In the current model, only the repository and issue-tracking types in the table expose those events. Repository rows use the pull-request, issue, and release events; Jira project rows use the send-to-doc and issue-status-change events; Linear uses issue creation and comments.

| Type | API value | Role | Requires | Automatic triggers |
| --- | --- | --- | --- | --- |
| GitHub App | `githubApp` | `git provider` | — | — |
| GitLab provider | `gitlabProvider` | `git provider` | — | — |
| Bitbucket provider | `bitbucketProvider` | `git provider` | — | — |
| Slack App | `slackApp` | `context source` | — | — |
| Atlassian Forge App | `atlassianForgeApp` | `context source` | — | — |
| GitHub repository | `githubRepo` | `git repository` | `GitHub App` | `pullRequests`, `newIssues`, `issueComments`, `releases` |
| GitHub personal access token | `githubAccessToken` | `git repository` | — | `pullRequests`, `newIssues`, `issueComments`, `releases` |
| GitLab repository | `gitlab` | `git repository` | — | `pullRequests`, `newIssues`, `issueComments`, `releases` |
| GitLab project | `gitlabProject` | `git repository` | `GitLab provider` | `pullRequests`, `newIssues`, `issueComments`, `releases` |
| Bitbucket repository | `bitbucketRepo` | `git repository` | — | `pullRequests`, `issueComments` |
| Bitbucket project | `bitbucketProject` | `git repository` | `Bitbucket provider` | `pullRequests`, `issueComments` |
| Documentation | `documentation` | `context source` | — | — |
| Notion | `notion` | `context source` | — | — |
| Google Drive | `gcp` | `context source` | — | — |
| AWS | `aws` | `context source` | — | — |
| Linear | `linear` | `context source` | — | `newIssues`, `issueComments` |
| Confluence | `confluence` | `context source` | — | — |
| Jira project | `jiraProject` | `context source` | — | `sendToDoc`, `issueStatusChange` |
| Azure Blob | `azureBlob` | `context source` | — | — |
| Atlassian Forge Jira project | `atlassianForgeJiraProject` | `context source` | `Atlassian Forge App` | `sendToDoc`, `issueStatusChange` |
| Slack Channel | `slackChannel` | `notifier` | `Slack App` | — |

## Footnotes

1. GitHub App and GitHub personal access token are the two GitHub auth paths.
2. GitLab provider and GitLab project split provider-backed and direct access.
3. Bitbucket provider and Bitbucket project split provider-backed and direct access.
4. `gcp` appears in the UI as Google Drive.
5. Slack Channel is the only Publication notifier.

## See also

[Sources](/c1-sources.md), [trigger and event types](/j9-trigger-and-event-types.md), and [API connections](/j3-api-connections.md).