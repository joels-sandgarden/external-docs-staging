---
title: Connect GitLab
url: "docs/connect-gitlab"
description: "Connect GitLab projects as Sources; Doc Holiday opens merge requests there."
---

Use this page when GitLab needs to feed Doc Holiday. For the shared model behind Sources, start with [Concepts](./a3-concepts.md) and [Sources](./c1-sources.md). On GitLab, Doc Holiday opens merge requests and keeps project Sources current.

## One token, many projects

1. Open **Sources**, then the **Providers** tab, and select **Add Provider**.
2. Choose **GitLab Access Token**.
3. Enter **Token Name** and **Access Token**, then save the provider.
4. Return to the **Sources** tab and select **Add Source**.
5. Choose **GitLab Project**.
6. Enter **Source Name**, **Project**, **Branch**, and **Publishing System**.
7. Choose the project in **Project**. Doc Holiday infers the provider token from the project you pick.
8. Repeat **Add Source** for each GitLab project that should use the same token.

If you need the supported publishing systems, see [Publishing systems](./d4-publishing-systems.md).

## One project with its own token

Use this option when one project needs its own token.

1. In the **Add Source** sheet with **GitLab Project** selected, use the **Click here ...** helper link to switch to the standalone GitLab form.
2. Enter **Source Name**, **Access Token**, **Project**, **Branch**, and **Publishing System**.
3. Save the Source.

This form covers exactly one project, and the token stays on that Source.

## Verify

Open **Sources** and confirm that the Source shows **Healthy**. If it does not, open [Manage connections](./c7-manage-connections.md).

## Next

Continue with [Create your first publication](./b5-create-your-first-publication.md).