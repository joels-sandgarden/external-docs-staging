# Trigger and event types

This reference page lists the trigger events Doc Holiday can react to and the connection types that support each one. See [/d2-configure-triggers.md](/d2-configure-triggers.md) for setup and [/j8-connection-types.md](/j8-connection-types.md) for the full source catalog.

| Event | Typical output | GitHub Repository | GitHub Repository (personal access token) | GitLab (multi-project access token) | GitLab Project | Bitbucket Repository (repository access token) | Bitbucket Project | Linear | Jira Read-Only | Jira Project |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Pull / Merge Requests | Page updates | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | — | — | — |
| New Issues | New pages or follow-up updates | ✓ | ✓ | ✓ | ✓ | — | — | ✓ | — | — |
| Issue Comments | Targeted updates | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | — | — |
| Releases | Release notes | ✓ | ✓ | ✓ | ✓ | — | — | — | — | — |
| Send to Doc | Page updates from a Jira issue | — | — | — | — | — | — | — | ✓ | ✓ |
| Issue status changes | Workflow page updates | — | — | — | — | — | — | — | ✓ | ✓ |

Doc Holiday does not offer a scheduled trigger. For recurring cadence, use CI through [/g1-github-action.md](/g1-github-action.md).