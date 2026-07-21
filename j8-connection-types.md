# Connection types

This reference lists every supported Doc Holiday connection type, its role, parent requirements, and automatic triggers.

| Type | API value | Role | Requires | Automatic triggers |
| --- | --- | --- | --- | --- |
| GitHub App | `githubApp` | `git provider` | — | — |
| GitLab provider | `gitlabProvider` | `git provider` | — | — |
| Bitbucket provider | `bitbucketProvider` | `git provider` | — | — |
| Slack App | `slackApp` | `notifier` | — | — |
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

## Notes

- GitHub App and GitHub personal access token are the two GitHub auth paths.
- GitLab provider and GitLab project split provider-backed and direct access.
- Bitbucket provider and Bitbucket project split provider-backed and direct access.
- The UI labels `gcp` as Google Drive.
- Slack Channel is the only publication notifier.

## See also

[Sources](/c1-sources.md), [trigger and event types](/j9-trigger-and-event-types.md), and [API connections](/j3-api-connections.md).