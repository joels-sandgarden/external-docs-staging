# Connect GitHub

Use this page when you need to connect GitHub to Doc Holiday. If the word Source is new, start with [Concepts](/a3-concepts.md). GitHub setup has two layers: install the GitHub App once for the organization, then add one repository Source for each repository Doc Holiday should read or write. Keep that order so the organization Source exists before you start wiring individual repositories, and so you can reuse the organization install for later repository Sources.

## Install the GitHub App

1. Open the GitHub setup flow and select **Install GitHub App**. That starts the organization-wide install and keeps the rest of the setup tied to the same GitHub account.
2. Choose the organization that owns the repositories you want Doc Holiday to use, then finish the GitHub prompts. When GitHub sends you back to Doc Holiday, continue with repository setup.
3. If Doc Holiday asks for admin help, select **Create Invite Link**. Copy the link and send it to an organization owner or GitHub App manager. They can open it, approve the app, and finish the install without changing the rest of your setup.

```text
SCREENSHOT PLACEHOLDER: connect-github/app-install.png
```

After installation, Doc Holiday returns you to the same flow so you can add repository Sources under the organization install. The app keeps the same organization context, so the next step stays tied to the right GitHub account.

## Add a repository Source

1. Open the repository Source form under the installed GitHub App. Use this form for each repository that belongs in the same GitHub organization.
2. Enter a **Source Name** that makes the repository easy to identify later, especially when one organization connects several repos. Pick a name that matches the repository or team that uses it. Clear names help when the same organization also connects a docs repo or a staging repo.
3. Select **Repository** from the picker. Doc Holiday fills in the repository and the default branch automatically. Use that default branch when the repository follows a single main line of work, or change **Branch** when a different branch should drive documentation.
4. Submit the form to create the repository Source. Repeat the same flow for every repository that should belong to the organization or publication.

```text
SCREENSHOT PLACEHOLDER: connect-github/repo-connection-form.png
```

If the repository list looks empty, return to the app install and confirm that the organization grant includes the repository you want. That usually means the app install does not yet cover the repository you expect.

## Option B: use a personal access token

Use this path when the GitHub App cannot be installed for the organization, or when an admin cannot finish the app install right away. This still creates a repository Source, but it uses a token instead of the app. It works best for recovery or for organizations that block the app install. The token path asks for the same repository details, so the Source behaves the same way after setup.

1. Enter a **Source Name** that identifies the Source clearly.
2. Paste the **Personal Access Token**.
3. Enter the repository in **Repository**. Use the repository path that matches the project you want Doc Holiday to use.
4. Choose **Branch** after the repository loads, then submit the form. The branch list appears once Doc Holiday can read the repository with the token.

If the token can reach more than one repository, pick the one you want Doc Holiday to keep reading or writing, then keep the branch aligned with that workflow.

## Verify

Open the Connections page and find the GitHub Source. Check the badge beside it. A working Source shows **Healthy**. If it shows **Unhealthy**, open [/c7-manage-connections.md](/c7-manage-connections.md) and fix the Source before you add another repository or create a publication. Use this check before moving on, because a healthy badge confirms the Source is ready for the next step. That check saves time before you create a publication, because later steps assume the Source is already healthy.

## Next

Next: [Create your first publication](/b5-create-your-first-publication.md).