# Trigger and event types

This reference page lists the trigger events Doc Holiday can react to and the source types that support each one. See /d2-configure-triggers.md for setup and /j8-connection-types.md for the full source catalog.

| Event | Typical output | GitHub Repository | GitHub Repository (personal access token) | GitLab (multi-project access token) | GitLab Project | Bitbucket Repository (repository access token) | Bitbucket Project | Linear | Jira Read-Only | Jira Project | Atlassian Forge Jira Project |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Pull / Merge Requests | Documentation updates | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | — | — | — | — |
| New issues | New documentation or follow-up updates | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | — | — | — |
| Issue comments | Targeted documentation updates | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | — | — | — |
| Releases | Release notes | ✓ | ✓ | ✓ | ✓ | — | — | — | — | — | — |
| Send to Doc | Documentation updates from Jira | — | — | — | — | — | — | — | ✓ | ✓ | ✓ |
| Issue status change | Workflow-driven documentation updates | — | — | — | — | — | — | — | ✓ | ✓ | ✓ |

Doc Holiday does not offer a scheduled trigger. For recurring cadence, use CI through /g1-github-action.md.