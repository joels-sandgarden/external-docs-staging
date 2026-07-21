# Connection types

This page lists each supported connection type, its app label, any required parent connection, and its automatic trigger events.

| Type | API value | Role | Requires | Automatic triggers |
| --- | --- | --- | --- | --- |
| GitHub Application | `githubApp` | git provider | — | — |
| GitHub Repository | `githubRepo` | git repository | GitHub Application | `TriggerEventPullRequests`, `TriggerEventNewIssues`, `TriggerEventIssueComments`, `TriggerEventReleases` |
| GitHub Repository | `githubAccessToken` | git repository | — | `TriggerEventPullRequests`, `TriggerEventNewIssues`, `TriggerEventIssueComments`, `TriggerEventReleases` |
| GitLab Access Token | `gitlabProvider` | git provider | — | — |
| GitLab Project | `gitlabProject` | git repository | GitLab Access Token | `TriggerEventPullRequests`, `TriggerEventNewIssues`, `TriggerEventIssueComments`, `TriggerEventReleases` |
| GitLab Project | `gitlab` | git repository | — | `TriggerEventPullRequests`, `TriggerEventNewIssues`, `TriggerEventIssueComments`, `TriggerEventReleases` |
| Bitbucket Workspace Access Token | `bitbucketProvider` | git provider | — | — |
| Bitbucket Project | `bitbucketProject` | git repository | Bitbucket Workspace Access Token | `TriggerEventPullRequests`, `TriggerEventIssueComments` |
| Bitbucket Project | `bitbucketRepo` | git repository | — | `TriggerEventPullRequests`, `TriggerEventIssueComments` |
| Atlassian Application | `atlassianForgeApp` | context source | — | — |
| Jira Read-Only | `jiraProject` | context source | — | `TriggerEventSendToDoc`, `TriggerEventIssueStatusChange` |
| Jira Project | `atlassianForgeJiraProject` | context source | Atlassian Application | `TriggerEventSendToDoc`, `TriggerEventIssueStatusChange` |
| Slack Application | `slackApp` | context source | — | — |
| Slack Channel | `slackChannel` | notifier | Slack Application | — |
| External Documentation | `documentation` | context source | — | — |
| Google Drive | `gcp` | context source | — | — |
| AWS (S3) | `aws` | context source | — | — |
| Notion | `notion` | context source | — | — |
| Linear | `linear` | context source | — | `TriggerEventNewIssues`, `TriggerEventIssueComments` |
| Confluence | `confluence` | context source | — | — |
| Azure Blob Storage | `azureBlob` | context source | — | — |

Footnotes:

- `githubRepo` and `githubAccessToken` both appear as `GitHub Repository`; `githubRepo` uses a GitHub Application parent, and `githubAccessToken` uses a personal access token.
- `gitlabProject` and `gitlab` both appear as `GitLab Project`; `gitlabProject` uses a GitLab Access Token parent, and `gitlab` uses a multi-project token.
- `bitbucketProject` and `bitbucketRepo` both appear as `Bitbucket Project`; `bitbucketProject` uses a Bitbucket Workspace Access Token parent, and `bitbucketRepo` uses a per-repository token.
- `gcp` is the API value behind `Google Drive`.
- `slackChannel` is the only connection type that can serve as a Publication notifier.

Related pages: [Sources](/c1-sources.md), [trigger and event types](/j9-trigger-and-event-types.md), and [API connections](/j3-api-connections.md).