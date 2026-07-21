# Sources

Doc Holiday reads from Sources, keeps a Publication current, and records the work in Work History. The Library supplies the shared guidance that shapes the pages it writes, so the final draft reflects both the source material and the way the organization wants content framed. This page explains what a Source is, how provider groups and child Sources fit together, and how freshness and health change what Doc Holiday can use.

## What a Source is

A Source is any system Doc Holiday can read. Sometimes that Source also becomes the docs destination for a Publication, which means Doc Holiday writes into it as part of keeping the documentation site current. That gives a Source three common roles in the product: a git repository that can provide context and receive documentation, a context system that feeds background only, and a Slack channel that carries notifications.

Each Source keeps one live setup. Doc Holiday treats that setup as the active way to reach the system, so the same Source does not point at two different places at once. That matters because a Publication may rely on the same provider in different ways across the workspace, but each Source still needs a single, clear identity. The Sources page reflects that idea by showing shared provider Sources first and the child Sources beneath them.

## Provider-level Sources and child Sources

GitHub, GitLab, and Bitbucket all use the same basic shape. Doc Holiday installs the provider once, then adds the repository or project Sources that live under it. Shared access stays with the provider, while the child Source names the exact repository or project that Doc Holiday should use. That keeps the model easier to understand when one provider supports many places at once.

The grouped list in the app makes that relationship obvious. A provider row shows the shared Source, and the rows below it show the child Sources that depend on it. GitHub starts with a GitHub App Source and then adds repository Sources. GitLab starts with a GitLab provider Source and then adds project Sources. Bitbucket follows the same pattern with provider, repository, and project Sources. Slack uses the same logic for notifications: Doc Holiday connects a Slack app first, then selects a channel Source underneath it for the messages that should reach a team.

This split gives a useful boundary between shared access and specific content. One provider can support more than one child Source, and the child Source can belong to a different Publication if the access and purpose fit. The app still keeps the provider visible at the top of the group, which helps when several Publications rely on the same starting point.

## Freshness and health

Doc Holiday keeps Sources fresh by re-reading them regularly, roughly every couple of hours for each Source, and by reading the latest source again before it writes. That way, the draft that appears in Work History stays close to the most recent state of the connected system instead of trailing behind it.

Health gives a simple answer to a simple question: can Doc Holiday use this Source right now? Each Source shows as Healthy or Unhealthy. When a Source turns Unhealthy, Doc Holiday skips it until someone fixes the problem and the Source becomes usable again. The health badge makes that state visible, and the management page covers the repair flow: [Manage connections](/c7-manage-connections.md).

That separation keeps failures from hiding in the background. A Source can still exist in the workspace, but it does not take part in the next read until it returns to Healthy. That keeps the result tied to the actual state of the Source instead of to a stale assumption in the app.

## Context Sources

Doc Holiday also reads several Sources only for context. Notion asks for an integration key. Confluence asks for a URL, username, and API token. Jira asks for a URL, email address, API token, and project key. Linear asks for an API key and a team. Google Drive asks for service account JSON, and the app lets you upload a file or paste the JSON directly. AWS asks for an access key ID, secret access key, and region. Azure Blob asks for an account name, account key, and container name.

These Sources help Doc Holiday understand the material around a change without making that material the docs destination itself. They often hold background, planning notes, reference text, or support information that sharpens the draft, while the Publication still writes into its own docs repository. That keeps the roles separate: one Source supplies context, another Source stores the published result, and the Library guides the wording that links them together.

External Documentation works differently from the other context Sources. It points at an existing hosted docs site by URL, and it can also use a username and password or token when the site needs protection. Doc Holiday reads that content as context, not as the target for a Publication. That makes it useful for product sites, help centers, and knowledge bases that sit outside the docs repository but still shape the draft.

### A note about documentation

Documentation can mean three different things in Doc Holiday: the External Documentation Source, the docs destination a Publication writes into, and the documentation output type. The output type has its own page at [Output types](/d3-output-types.md). Keeping those meanings separate avoids confusion when more than one kind of Source appears on the same screen.

## Set up a source

- [GitHub](/b2-connect-github.md)
- [GitLab](/b3-connect-gitlab.md)
- [Bitbucket](/b4-connect-bitbucket.md)
- [Notion](/c2-connect-notion.md)
- [Confluence and Jira](/c3-connect-confluence-and-jira.md)
- [Linear](/c4-connect-linear.md)
- [Google Drive](/c5-connect-google-drive.md)
- [Cloud storage](/c6-connect-cloud-storage.md)