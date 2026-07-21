# Sources in Doc Holiday

Doc Holiday uses Sources for every connected system it can read from, and sometimes write to. A Publication points at the Sources it should read for context, the connected git repository it should write into, and an optional Slack Channel Source for notifications. That makes a Source the common shape for a repository, a context system, a notification channel, or the repository that receives documentation.

One Publication can mix those roles. It can read from a GitHub repository for change history, from Notion or Confluence for background, from Jira or Linear for tracking notes, and from Google Drive or cloud storage for source material. A Slack Channel Source can then carry the notification trail.

A Publication can choose any connected git repository as its docs destination. GitHub, GitLab, and Bitbucket all fit that pattern, and Doc Holiday still treats the destination as a Source rather than a special case. The Publication decides which connected repository supplies context and which connected repository receives the documentation output.

In the Sources list, each row shows an icon, a name, and a health badge. When a child Source sits under a provider, the parent appears underneath it so the relationship stays visible at a glance.

## Provider Sources and the Sources under them

Provider Sources work as the first step in an install-once flow. You connect the provider once, then add the repositories, projects, or channels that belong under it. The form changes to match the Source type you selected, so the provider setup and the child Source setup stay separate.

That pattern shows up across the supported Source types. GitHub App connects once, then repositories sit beneath it. GitLab provider connects once, then GitLab projects sit beneath it. Bitbucket provider connects once, then Bitbucket repositories and Bitbucket projects sit beneath it. Slack App follows the same idea for notifications: you connect the Slack App once, then choose the Slack Channel Source that should receive updates.

This structure keeps the setup model simple. The provider carries the shared access, and the child Source names the specific repository, project, or channel that Doc Holiday should use. If a provider already exists, the child Source reuses it instead of asking for the same access again.

That is why the form changes by Source type. A provider asks for the shared access first, and the child Source asks for the one repository, project, or channel that should use it. The setup feels different from provider to provider, but the rule never changes: connect once, then choose the exact child item.

## Freshness and health

Doc Holiday rereads connected Sources roughly every couple of hours, and it checks the latest Source again before it writes. That keeps the visible documentation close to the current state of the connected systems without making the reader manage refresh timing by hand.

Every Source also reports a health state. Healthy Sources stay available for Publications. Unhealthy Sources stay out of the way until they work again. See [Manage Sources](/c7-manage-connections.md) for the UI that shows and repairs Source health.

When a health badge turns Unhealthy, Doc Holiday leaves that Source out of the next pass. When it turns Healthy again, the Source can take part in the next read. That keeps the visible state tied to the actual Source instead of a remembered setting in the app.

## External Documentation

External Documentation is a read only Source for hosted docs sites. Enter the site URL, and optionally a username and password when the site needs protection. Doc Holiday reads that Source as context only; it does not write back to it.

External Documentation fits differently from a repository or a chat channel. It gives Doc Holiday outside context, such as product copy, help article text, or a hosted knowledge site, but it never becomes a write target. Use it when the site can help the draft without becoming part of the docs repo itself.

## A note about `documentation`

The word `documentation` can point to three different things in Doc Holiday: the External Documentation Source, the docs destination repository in a Publication, or the documentation output type. For the output type sense, see [Output types](/d3-output-types.md).

That distinction matters when a Publication uses more than one kind of Source at the same time. A docs repository stores the output, a context Source informs the draft, and the output type decides what Doc Holiday should write. The labels stay separate so the app can show each role clearly.

## Set up a source

- [Connect GitHub](/b2-connect-github.md)
- [Connect GitLab](/b3-connect-gitlab.md)
- [Connect Bitbucket](/b4-connect-bitbucket.md)
- [Connect Notion](/c2-connect-notion.md)
- [Connect Confluence and Jira](/c3-connect-confluence-and-jira.md)
- [Connect Linear](/c4-connect-linear.md)
- [Connect Google Drive](/c5-connect-google-drive.md)
- [Connect cloud storage](/c6-connect-cloud-storage.md)