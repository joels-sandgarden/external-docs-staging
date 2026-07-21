# Connect GitLab sources in Doc Holiday

Use this guide when GitLab needs to feed Doc Holiday with project changes and keep documentation current. Doc Holiday uses Sources for GitLab projects; see [Concepts](/a3-concepts.md) for the shared model.

On GitLab, Doc Holiday opens merge requests rather than pull requests.

## Main path: create a GitLab Access Token and GitLab Project Source

1. Open **Sources**, then add **GitLab Access Token**.
2. Enter **Token Name** and **Access Token**, then save the access token.
3. Add **GitLab Project** under that token.
4. Fill in **Source Name**, **Project**, **Branch**, and **Publishing System**.
5. Select the project and branch Doc Holiday should watch, then save the Source.
6. Repeat the project step for each GitLab project that should use the same provider.

If the **Publishing System** choice needs a refresher, see [Publishing systems](/d4-publishing-systems.md).

## Option: use one access token for multiple projects

Use **GitLab** and select **Connect with Personal Access Token** when one token should create Sources for multiple projects.

## Verify

Open [Sources](/c1-sources.md) and confirm that the new Source shows **Healthy**. If it shows **Unhealthy**, open [Manage connections](/c7-manage-connections.md) and update the Source before continuing.

## Next

Continue with [Create your first publication](/b5-create-your-first-publication.md).