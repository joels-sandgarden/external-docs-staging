---
title: Connect Bitbucket
url: "docs/connect-bitbucket"
description: "Connect Bitbucket via a workspace token provider or per-project tokens."
---

Use this guide to connect Bitbucket Sources in Doc Holiday. Bitbucket Sources react only to pull requests and pull request comments; issue and release triggers do not work. See [Configure triggers](./d2-configure-triggers.md).

A Bitbucket setup uses two layers: a workspace access-token provider first, then Bitbucket Project connections underneath it. Use the workspace path when one token should cover more than one project. Use Option B when one project needs its own token.

## Option A: workspace access-token provider, then Bitbucket Project connections

1. In Sources, select **Add Provider**.
2. In the sheet titled **Create Provider**, choose **Bitbucket Workspace Access Token**.
3. Enter **Token Name**, **Workspace**, and **Access Token**.
4. Select **Save Changes**, then select **Add Source**.
5. In the sheet titled **Create Source**, choose **Bitbucket Repository**.
6. Enter **Source Name**, then choose **Repository** and the **Select a repository** picker.
7. Select a **Branch** with **Select branch**, then choose a **Publishing System** with **Select a publishing system**.
8. Turn on **Pause Background Work for Source** only if the Source should stay idle. Select **Save Changes** to finish the Source.

This path keeps one workspace token above the Bitbucket Project connections, so several projects can share the same access token.

## Option B: repository access token

1. In Sources, select **Add Source**.
2. In the sheet titled **Create Source**, choose **Bitbucket Repository**.
3. Enter **Source Name**, **Repository**, and **Repository Access Token**.
4. Select a **Branch** and a **Publishing System**.
5. Select **Save Changes** to finish the Source.

Use this option when one repository needs its own token.

## Verify

Open the Sources page and confirm the Source shows **Healthy**. If it shows **Unhealthy**, open [Manage connections](./c7-manage-connections.md).

## Next

Continue with [Create your first publication](./b5-create-your-first-publication.md).