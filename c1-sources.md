# Sources

## What sources are

Doc Holiday treats a Source as a connected system that supplies information or receives updates. Some sources act as repositories that Doc Holiday can read and write. Others only provide context, and Doc Holiday reads them without changing them. Slack Channel is the source that carries notifications.

For the shared vocabulary behind this page, see [Concepts](/a3-concepts.md).

## Provider connections and child sources

Some sources come in pairs. A provider holds shared access once, then Doc Holiday reuses that access for each individual repository or project underneath it. The UI shows provider labels and source labels separately, so the shared connection stays distinct from the child connection it powers.

The pattern is the same across the supported providers:

- GitHub Application provides access for GitHub Repository sources.
- GitLab Access Token provides access for GitLab Project sources.
- Bitbucket Workspace Access Token provides access for Bitbucket Project sources.
- Atlassian Application provides access for Jira Project sources.
- Slack Application provides access for Slack Channel sources.

That split keeps workspace access in one place and lets a team add or remove individual repositories, projects, or channels without setting up the parent connection again.

## Freshness and health

Doc Holiday rereads connected sources on a background cadence, roughly every couple of hours for each source. Before it writes, it refreshes the stalest source first so the draft starts from the newest available content.

Every source also shows a health state. Healthy means Doc Holiday can use the source. Unhealthy means Doc Holiday skips it until someone fixes the problem. For the operational details around credentials, health, and deletion, see [Manage connections](/c7-manage-connections.md).

## External Documentation

External Documentation connects Doc Holiday to an existing hosted docs site by URL. It reads that site for context only. Optional username and password fields support protected sites, but the source never publishes content back to that site.

## Documentation can mean more than one thing

Documentation has three meanings in Doc Holiday. It can mean the External Documentation source, the docs destination repository that a Publication writes into, or the documentation output type [Documentation](/d3-output-types.md). For the Publication model, see [Publications](/d1-publications.md).

## Set up a source

- [GitHub](/c2-github.md)
- [GitLab](/c3-gitlab.md)
- [Bitbucket](/c4-bitbucket.md)
- [Notion](/c5-notion.md)
- [Confluence and Jira](/c6-confluence-jira.md)
- [Linear](/c8-linear.md)
- [Google Drive](/c9-google-drive.md)
- [Cloud storage](/c10-cloud-storage.md)