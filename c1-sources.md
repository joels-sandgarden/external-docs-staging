# Sources

Doc Holiday reads from Sources, keeps a Publication current, and records the work in Work History. The Library supplies the shared guidance that shapes the pages it writes, so the result reflects both the source material and the organization’s own editorial choices. This page explains what a Source can be, how provider groups work, and how freshness and health affect what Doc Holiday uses.

## What a Source is

A Source is a system Doc Holiday can read. In some cases, a Source also serves as the docs destination for a Publication, so Doc Holiday writes into it while it maintains the documentation site. That gives Sources three common roles: a git repository Doc Holiday reads and writes, a context system Doc Holiday reads only, and a Slack channel Doc Holiday uses for notifications.

Each Source keeps one live setup. Doc Holiday treats that setup as the only active way to reach the system, which keeps the shape of the Source simple and predictable. When you look at the Sources page, the app presents shared provider Sources first and the child Sources beneath them.

## Provider-level Sources and child Sources

GitHub, GitLab, and Bitbucket all use a model where Doc Holiday installs the provider once, then adds individual repository or project Sources underneath it. That split keeps shared access in one place while each repo or project keeps its own identity.

The grouped list in the app shows that structure clearly. A provider row shows the shared Source, and the rows below it show the child Sources that belong to that provider. GitHub uses a provider Source and then repository Sources. GitLab uses a provider Source and then project Sources. Bitbucket uses a provider Source and then repository or project Sources. Slack follows the same pattern for notifications: Doc Holiday connects a Slack app first, then it selects a channel Source under it for the messages that reach a team.

## Freshness and health

Doc Holiday keeps Sources fresh by re-reading them regularly, about every couple of hours for each Source, and by reading the latest source again before it writes. That means the draft that appears in Work History stays close to the most recent content Doc Holiday can see.

Health gives a quick answer to a simple question: can Doc Holiday use this Source right now? Each Source shows as Healthy or Unhealthy. When a Source turns Unhealthy, Doc Holiday skips it until someone fixes the problem and the Source becomes usable again. For more on managing that state, see [Manage connections](/c7-manage-connections.md).

## Context Sources

Doc Holiday also reads several Sources only for context. Notion asks for an integration key. Confluence asks for a URL, username, and API token. Jira asks for a URL, email address, API token, and project key. Linear asks for an API key and a team. Google Drive asks for service account JSON, and the app lets you upload a file or paste the JSON directly. AWS asks for an access key ID, secret access key, and region. Azure Blob asks for an account name, account key, and container name.

External Documentation works differently from those context Sources. It points at an existing hosted docs site by URL, and it can also use a username and password or token when the site needs protection. Doc Holiday reads that content as context, not as the target for a Publication.

### A note about documentation

Documentation can mean three different things in Doc Holiday: the External Documentation Source, the docs destination a Publication writes into, and the documentation output type. The output type has its own page at [Output types](/d3-output-types.md).

## Set up a source

- [GitHub](/b2-connect-github.md)
- [GitLab](/b3-connect-gitlab.md)
- [Bitbucket](/b4-connect-bitbucket.md)
- [Notion](/c2-connect-notion.md)
- [Confluence and Jira](/c3-connect-confluence-and-jira.md)
- [Linear](/c4-connect-linear.md)
- [Google Drive](/c5-connect-google-drive.md)
- [Cloud storage](/c6-connect-cloud-storage.md)