---
title: Sources
url: "docs/sources"
description: "What Doc Holiday reads and writes: connection roles, freshness, and health."
---

## What sources are

Doc Holiday treats a Source as a connected system that either receives documentation or supplies context. A writable Source gives Doc Holiday a place to write finished documentation. A read only Source gives Doc Holiday background material, and a Slack Channel can also carry notifications.

Other Sources stay read only and feed background material into Doc Holiday. Notion, Confluence, Linear, Google Drive, AWS (S3), and Azure Blob Storage all fit that shape when a team needs context instead of a writable destination.

Doc Holiday uses that mix of Sources in one workflow. A Publication points at one Source for the docs destination and at other Sources for context, so the same page can describe writable Sources and read only Sources without treating them as separate ideas.

That single model helps people who keep product notes in one place, source content in another, and the Publication destination somewhere else. Doc Holiday can read across those places without making readers learn three separate setup paths.

For the shared vocabulary behind this page, see [Concepts](./a3-concepts.md).

## Provider connections and child sources

Some Sources use a shared-access pattern. A parent provider holds the shared access once, and each child Source uses that access for its own repository or project. The UI shows provider labels and Source labels separately, so the parent stays distinct from the child it powers.

This split keeps workspace access in one place. It also lets a team add or remove individual repositories, projects, or channels without setting up the parent again or changing the rest of the workspace.

The parent provider usually holds the shared workspace or app access, while the child Source keeps its own name and settings. The child inherits the access it needs from the provider, which gives Doc Holiday a clean boundary between shared permissions and individual content Sources.

The pattern is the same across the supported provider families:

- GitHub Application provides access for GitHub Repository Sources.
- GitLab Access Token provides access for GitLab Project Sources.
- Bitbucket Workspace Access Token provides access for Bitbucket Project Sources.
- Atlassian Application provides access for Jira Project Sources.
- Slack Application provides access for Slack Channel Sources.

The same structure appears wherever Doc Holiday needs one shared permission set and many child Sources.

The pattern also keeps the setup story easy to follow. Once the provider exists, the child Source only needs the fields that belong to that specific repository, project, or channel, which keeps repeated setup work to a minimum.

## Freshness and health

Doc Holiday rereads connected Sources on a background cadence, roughly every couple of hours for each Source. That keeps it close to the current state of connected systems without waiting for manual refreshes.

Each Source also shows a health state. Healthy means Doc Holiday can use the Source. Unhealthy means Doc Holiday stops rereading that Source until someone fixes the problem, so its information goes stale instead of fresh. A draft can still use the healthy Sources, while the unhealthy Source stays out of the write cycle until it recovers.

The health badge gives a quick answer to a simple question: can Doc Holiday trust this Source right now? If the answer changes, Doc Holiday stops rereading that Source until the health problem clears. That keeps drafts from mixing current content with stale or inaccessible material.

For operational details around credentials, health, and deletion, see [Manage connections](./c7-manage-connections.md).

That page covers the day to day maintenance work, while this page stays with the idea of what health means and why Doc Holiday skips an unhealthy Source instead of guessing.

## External Documentation

External Documentation connects Doc Holiday to an existing hosted docs site by URL. It reads that site as context and nothing more. Optional username and password fields support protected sites, which lets Doc Holiday reach material behind a login.

That makes External Documentation useful when product notes, policies, or design references live in another system. Doc Holiday can read those pages alongside code and repository history without turning that external site into a publishing target.

This Source never publishes content back to the remote site, so it works as a read only reference rather than another docs destination.

If a team already keeps docs context in a managed site, External Documentation lets Doc Holiday read that material without copying it into another system first.

## Documentation can mean more than one thing

Documentation has three meanings in Doc Holiday. It can mean External Documentation, which is a Source. It can also mean the docs destination repository that a Publication writes into. Finally, it can mean the Documentation output type [Documentation](./d3-output-types.md), which is one of the outputs a Publication can ask Doc Holiday to produce.

That distinction matters because the product uses the same word in different parts of the workflow. Think of the Publication's docs repository as the place where the final page lives, and think of Documentation output as the kind of content the Publication asks Doc Holiday to produce. For the Publication model behind that choice, see [Publications](./d1-publications.md).

That wording prevents confusion when the UI asks for a documentation source, a Publication destination, or a documentation output selection in the same flow.

## Set up a source

When a team needs to add a new Source, the setup pages show the fields, validation, and workspace selection specific to that system. These pages cover setup, so this list stays short.

- [GitHub](./b2-connect-github.md)
- [GitLab](./b3-connect-gitlab.md)
- [Bitbucket](./b4-connect-bitbucket.md)
- [Notion](./c2-connect-notion.md)
- [Confluence and Jira](./c3-connect-confluence-and-jira.md)
- [Linear](./c4-connect-linear.md)
- [Google Drive](./c5-connect-google-drive.md)
- [Cloud storage](./c6-connect-cloud-storage.md)
