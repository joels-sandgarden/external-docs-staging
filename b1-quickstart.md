# Quickstart

This quickstart follows the GitHub path from sign-in to a merged Doc Holiday-written document.

1. Sign in at `app.doc.holiday`, select **Get started** on **Ready to get your docs in a row?**, and continue to **Add Source(s)**.
2. On the source screen, select **GitHub**, then choose **Install GitHub App**. In the repository picker, use **Search repositories...**, **Select all**, and **Add Sources** to finish the connection.

GitLab and Bitbucket each have a matching setup guide: [Connect GitLab](/b3-connect-gitlab.md) and [Connect Bitbucket](/b4-connect-bitbucket.md).

![The Add Source(s) onboarding step with a GitHub repository selected](/screenshots/quickstart/onboarding-connect.png)

3. Create the publication by filling in **What would you like to name this publication?**, choosing **Which repositories are sources of changes for a single project or product?**, pointing Doc Holiday at **Where should Doc Holiday write its words?**, choosing **Documentation** under **What would you like Doc Holiday to write?**, answering **What publishing system does** *your publication* **use?**, and selecting **Create Publication**. For the full setup, see [Create your first publication](/b5-create-your-first-publication.md).

![The publication create form: name, source repositories, write destination, and output types](/screenshots/quickstart/publication-form.png)

4. On **Verify your setup**, select **Create Test Pull Request** once and wait for **Test successful!**; a **View Pull Request** link appears. Continue through **Choose your plan** and **Go to the Doc Holiday App**. On the Bring Your Own Key and Open Source plans an **Add your AI provider key** step appears on the way — see [Add your OpenAI key](/b6-add-your-openai-key.md).

5. In Work History, select **Create Work Request**; the sheet opens as **New Work Request**. Choose your publication under **Publication**, then enter `Write a getting-started page for this project` in **Description**. Select **Submit Request** and wait for the **Work Request Created** success message. The entry then appears in Work History with the staged status **Ready for Review**.

![The New Work Request sheet with a publication selected and a request typed in Description](/screenshots/quickstart/create-work-request.png)

![The Work History list showing new entries for the publication](/screenshots/quickstart/work-history-staged.png)

6. Open the entry, select the **Files** tab, and review the draft there. See [Review and revise](/f3-review-and-revise.md) for the next step. When it is time to publish, select **Open Pull Request**. The dialog shows **Open Pull Request**, **Confirm**, and **Cancel**; choose **Confirm** and merge the resulting GitHub pull request.

## Verify

The merged file is visible in the repository.

## Next

Next: [Request work in the app](/f2-request-work-in-the-app.md).