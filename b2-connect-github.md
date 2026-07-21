# Connect GitHub

Use this page when you need to connect GitHub to Doc Holiday. If Source is new, start with [Concepts](/a3-concepts.md). GitHub setup works in two layers: install the GitHub App once for the organization, then add one repository Source for each repository Doc Holiday should read or write.

## Install the GitHub App

1. Open the GitHub setup flow and select **Install GitHub App**.
2. Finish the GitHub install in the organization that should own the Source.
3. If the account does not have organization owner or app manager access, select **Create Invite Link**. Copy the link and send it to an organization owner or GitHub App manager so they can complete installation.

```text
SCREENSHOT PLACEHOLDER: connect-github/app-install.png
```

## Add a repository Source

1. Open the repository Source form under the installed GitHub App.
2. Enter a **Source Name** that makes the repository easy to recognize later.
3. Select **Repository** from the picker. Doc Holiday fills in the repository and the default branch automatically.
4. Review **Branch**. Change it only when the Source should use a branch other than the default.
5. Submit the form to create the repository Source.

```text
SCREENSHOT PLACEHOLDER: connect-github/repo-connection-form.png
```

## Option B: use a personal access token

Use this path when the GitHub App cannot be installed for the organization. Create a repository Source with **Source Name**, **Personal Access Token**, **Repository**, and **Branch**.

1. Enter a **Source Name**.
2. Paste the **Personal Access Token**.
3. Enter the repository in **Repository**.
4. Choose **Branch** and submit the form.

## Verify

Open the Connections page and check the Source badge for the GitHub setup. A healthy Source shows **Healthy**. If the badge shows **Unhealthy**, open [/c7-manage-connections.md](/c7-manage-connections.md) and fix the Source before adding more repositories.

## Next

Next: [Create your first publication](/b5-create-your-first-publication.md).