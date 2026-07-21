# Connect Bitbucket Sources

Use this guide to connect Bitbucket Sources in Doc Holiday. Bitbucket Sources react only to pull requests and pull request comments; issue and release triggers do not apply. See [Configure triggers](/d2-configure-triggers.md).

If the Source already exists, update it in [Manage connections](/c7-manage-connections.md).

## Option A: workspace access token and Bitbucket Project

1. Open **Sources**, then select the **Providers** tab.
2. Select **Add Provider**.
3. Choose **Bitbucket Workspace Access Token**.
4. Enter **Token Name**, **Workspace**, and **Access Token**.
5. Select **Save Changes**.
6. Open the **Sources** tab and select **Add Source**.
7. Choose **Bitbucket Project**.
8. Enter **Source Name**.
9. Select **Repository**.
10. Select **Branch**.
11. Select **Publishing System**.
12. Select **Save Changes**.

Use this path when one workspace token should cover more than one project.

## Option B: repository access token for one repository

1. Open **Sources** and select **Add Source**.
2. Choose **Bitbucket Project**.
3. Select **Click here to connect with a repository access token instead**.
4. Enter **Source Name**, **Repository Access Token**, and **Repository**.
5. Select **Branch**.
6. Select **Publishing System**.
7. Select **Save Changes**.

Use this path when one repository needs its own access token.

## Verify

Open the **Sources** page and confirm the Source shows **Healthy**.

## Next

Continue with [Create your first publication](/b5-create-your-first-publication.md).