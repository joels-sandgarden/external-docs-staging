# Connect GitLab sources in Doc Holiday

Use this guide when GitLab needs to feed Doc Holiday with project changes and keep documentation current. Doc Holiday uses Sources for GitLab projects; see [Concepts](/a3-concepts.md) for the shared model.

On GitLab, Doc Holiday opens merge requests rather than pull requests.

## Main path: create a provider and a project Source

1. Open **Sources**, then add a GitLab provider Source.
2. Enter **Token Name** and **Access Token**, then save the provider.
3. Add a GitLab Project Source under that provider.
4. Fill in **Source Name**, **Project**, **Branch**, and **Publishing System**.
5. Select the project and branch Doc Holiday should watch, then save the Source.
6. Repeat the project step for each GitLab project that should use the same provider.

If the **Publishing System** choice needs a refresher, see [Publishing systems](/d4-publishing-systems.md).

## Option: use one access token for multiple projects

Use **Connect with Personal Access Token** when one token should create Sources for multiple projects.

## Verify

Open [Sources](/c1-sources.md) and confirm that the new Source shows **Healthy**. If it shows **Unhealthy**, open the Manage connections page and update the Source before continuing.

## Next

Continue with [Create your first publication](/b5-create-your-first-publication.md).