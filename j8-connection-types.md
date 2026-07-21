# Connection types

This catalog follows the current connection type enumeration. It lists the supported API values the product accepts today and omits Zendesk, which this page does not treat as a supported type.

The table keeps the label and API value side by side so the catalog stays usable as a lookup page. The label column matches the user-facing name in the product, and the API value column preserves the exact machine value that the system stores and returns.

The Role column groups each type by its broader product area. Git provider covers the source control parent types, git repository covers repository-level connections, context source covers the services that feed content or issue data into documentation workflows, and notifier covers the connection type that supports publication delivery.

The Requires column names the parent connection when one exists. A blank entry means the type stands alone. The Automatic triggers column draws directly from the trigger-event map, so it lists only the events that the system can emit for that type and leaves blank entries where no automatic event applies.

Read the catalog as an index rather than a procedure. Each row identifies one supported type, its exact API value, the visible label, the role group, any parent requirement, and the trigger events linked to that type. When two rows share the same label, the table and footnotes separate the alternative API values and parent relationships that keep them distinct.

The table keeps provider and child rows adjacent so the parent requirement stays visible at a glance. That arrangement helps readers compare each type with its upstream connection without scanning across the page.

The catalog does not restate the separate source, trigger, or API pages. Those pages define the broader model, while this page keeps the connection type list, the visible labels, and the structural differences that matter when selecting a type.

The footnotes preserve overlapping labels that the product uses for multiple API values. They keep the shared names readable without adding a second table, and they point out the notifier role that only one connection type can fill.

The same label can point to more than one API value. The table and footnotes keep those pairs distinct without adding extra narrative, which helps the page remain a lookup reference rather than a guided workflow.

This layout keeps the page stable as the supported list changes, because new rows can fit the same five column pattern.

Each provider parent sits beside its child types, so the required parent stays visible at a glance. The API value separates rows that share a label but differ by parent or trigger support.

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

The cross-links below place this page beside the source, trigger, and API references, so the catalog stays compact while still connecting to the surrounding documentation.

See also: [Sources](/c1-sources.md), [trigger and event types](/j9-trigger-and-event-types.md), and [API connections](/j3-api-connections.md).