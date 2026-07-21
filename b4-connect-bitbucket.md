# Connect Bitbucket

Use this guide to connect Bitbucket Sources in Doc Holiday. Bitbucket Sources react only to pull requests and pull request comments; issue and release triggers do not work. See [Configure triggers](/d2-configure-triggers.md).

A Bitbucket setup uses two layers: a workspace access-token provider first, then repository Sources underneath it. Use the workspace path when one token should cover more than one repository. Use Option B when one repository needs its own token.

## Option A: workspace provider, then repository Sources

1. In Sources, select **"Add Provider"**.
2. In the sheet titled **"Create Provider"**, choose **"Bitbucket Workspace Access Token"**.
3. Enter **"Token Name"**, **"Workspace"**, and **"Access Token"**.
4. Save the provider, then select **"Add Source"**.
5. In the sheet titled **"Create Source"**, choose **"Bitbucket Repository"**.
6. Enter **"Source Name"**, then choose **"Repository"** and the **"Select a repository"** picker.
7. Select a **"Branch"** with **"Select branch"**, then choose a **"Publishing System"** with **"Select a publishing system"**.
8. Turn on **"Pause Background Work for Source"** only if the Source should stay idle. Finish by saving the Source.

This path keeps one workspace token above the repository Sources, so several repository Sources can share the same Bitbucket access.

## Option B: repository access token

1. In Sources, select **"Add Source"**.
2. In the sheet titled **"Create Source"**, choose **"Bitbucket Repository"**.
3. Enter **"Source Name"**, **"Repository"**, and **"Repository Access Token"**.
4. Select a **"Branch"** and a **"Publishing System"**.
5. Save the Source.

Use this option when one repository needs its own token.

## Verify

Open the Sources page and confirm the Source shows **Healthy**. If it shows **Unhealthy**, open [Manage connections](/c7-manage-connections.md).

## Next

Continue with [Create your first publication](/b5-create-your-first-publication.md).