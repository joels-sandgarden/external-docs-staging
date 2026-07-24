---
title: Connect GitHub
url: "docs/connect-github"
description: "Install the GitHub Application and connect repositories to Doc Holiday."
---

Use this page when a Publication needs one or more GitHub repository Sources. Install the GitHub Application first, then add one repository Source for each repository Doc Holiday should read or write. If the word Source is new, start with [Concepts](./a3-concepts.md).

## Install the GitHub Application

1. Open the GitHub setup flow and select **Install GitHub Application**.
2. Choose the GitHub organization that owns the repositories, then complete the GitHub prompts.
3. If the account does not have organization owner or app manager access, select **Create Invite Link**. Copy the link and send it to someone who can approve the installation.

![GitHub's Install doc.holiday screen asking where to install the app](/screenshots/connect-github/app-install.png)

After installation, Doc Holiday returns to the same setup flow with the organization selected.

## Add a repository Source

1. Open the repository Source form under the installed GitHub Application.
2. Enter a **Source Name** that matches the repository or team that will use it.
3. Select **Repository** and choose the repository that belongs in the Source.
4. Review the **Branch** value. Doc Holiday fills in the default branch automatically. Change it only when another branch should drive documentation.
5. Select **Save Changes** to create the Source. Repeat the same steps for each repository that needs its own Source.

![The Create Source form for a GitHub Repository: repository, branch, and publishing system fields](/screenshots/connect-github/repo-connection-form.png)

If the repository list is empty, return to the GitHub Application install and confirm that the organization grant includes the repository you expect.

## Use a personal access token

Use this path when the GitHub Application cannot be installed for the organization. It still creates a repository Source, but it uses a personal access token instead.

1. Enter a **Source Name** that clearly identifies the repository.
2. Paste the **Personal Access Token**.
3. Enter the repository path in **Repository**.
4. Review the **Branch** after the repository loads, then select the branch that should drive documentation.
5. Select **Save Changes**.

Keep the repository and branch aligned with the work that the Source should cover.

## Verify

1. Open **Sources**.
2. Find the GitHub Source.
3. Check the badge beside it.
4. Continue when the badge reads **Healthy**.
5. If the badge reads **Unhealthy**, open [Manage connections](./c7-manage-connections.md) and fix the Source before adding another repository or creating the first Publication.

## Next

Next: [Create your first publication](./b5-create-your-first-publication.md).

---

<!-- doc-holiday-watermark -->
<p align="center">
  <a href="https://doc.holiday">
    <img alt="Doc Holiday logo" src="https://doc.holiday/assets/docs-by-doc-holiday.png" width="200">
  </a>
</p>
<p align="center">Docs authored by <a href="https://doc.holiday">Doc Holiday</a></p>
