# Sources

## What sources are

Doc Holiday treats a Source as a connected system that contributes content or receives notifications. A source can be a repository that Doc Holiday reads and writes, a context system it only reads, or the Slack Channel that carries notifications.

Other sources stay read only and feed background material into Doc Holiday. Notion, Confluence, Linear, Google Drive, AWS (S3), and Azure Blob Storage all fit that shape when a team needs context instead of a writable destination.

For the shared vocabulary behind this page, see [Concepts](/a3-concepts.md).

## Provider connections and child sources

Some sources come in pairs. A provider holds shared access once, then Doc Holiday reuses that access for each individual repository or project underneath it. The UI shows provider labels and source labels separately, so the shared connection stays distinct from the child connection it powers.

That split keeps workspace access in one place. It also lets a team add or remove individual repositories, projects, or channels without setting up the parent connection again or changing the rest of the workspace.

The pattern is the same across the supported providers:

- GitHub Application provides access for GitHub Repository sources.
- GitLab Access Token provides access for GitLab Project sources.
- Bitbucket Workspace Access Token provides access for Bitbucket Project sources.
- Atlassian Application provides access for Jira Project sources.
- Slack Application provides access for Slack Channel sources.

The same structure appears wherever Doc Holiday needs one shared permission set and many child sources.

## Freshness and health

Doc Holiday rereads connected sources on a background cadence, roughly every couple of hours for each source. That keeps it close to the current state of the connected systems without waiting for manual refreshes.

Before it writes, Doc Holiday refreshes the stalest source first. That extra pass matters when several sources feed one Publication, because the first draft should start from the newest available material from every place it reads.

Every source also shows a health state. Healthy means Doc Holiday can use the source. Unhealthy means Doc Holiday leaves it out of the write cycle until someone fixes the problem. If a source stays unhealthy, the next draft can still use the healthy sources, but the missing source will not contribute until it recovers.

For the operational details around credentials, health, and deletion, see [Manage connections](/c7-manage-connections.md).

## External Documentation

External Documentation connects Doc Holiday to an existing hosted docs site by URL. It reads that site as context and nothing more. Optional username and password fields support protected sites, which lets Doc Holiday reach material that sits behind a login.

This source never publishes content back to the remote site, so it works as a read only reference rather than another docs destination.

## Documentation can mean more than one thing

Documentation has three meanings in Doc Holiday. It can mean External Documentation, which is a source. It can also mean the docs destination repository that a Publication writes into, which gives the Publication its target. Finally, it can mean the documentation output type [Documentation](/d3-output-types.md), which is one of the outputs a Publication can ask Doc Holiday to produce.

That distinction matters because the product uses the same word in different parts of the workflow. For the Publication model behind that choice, see [Publications](/d1-publications.md).

## Set up a source

When a team needs to add a new source, the provider page shows the fields and checks specific to that system. These pages cover setup, so this list stays short.

- [GitHub](/c2-github.md)
- [GitLab](/c3-gitlab.md)
- [Bitbucket](/c4-bitbucket.md)
- [Notion](/c5-notion.md)
- [Confluence and Jira](/c6-confluence-jira.md)
- [Linear](/c8-linear.md)
- [Google Drive](/c9-google-drive.md)
- [Cloud storage](/c10-cloud-storage.md)