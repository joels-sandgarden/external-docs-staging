---
title: Connect GitLab
url: "docs/connect-gitlab"
description: "Connect GitLab projects as Sources; Doc Holiday opens merge requests there."
---

Use this page to connect GitLab as a Source in Doc Holiday. For the shared model behind Sources, start with [Concepts](./a3-concepts.md) and [Sources](./c1-sources.md). On GitLab, Doc Holiday opens merge requests, GitLab's term for pull requests, and each project Source stays current.

## One token, many projects

Use this path when one GitLab access token should cover several project Sources.

1. Open **Sources**, then the **Providers** tab, and select **Add Provider**.
2. Choose **GitLab Access Token**.
3. Enter **Token Name** and **Access Token**. Select **Save Changes**.
4. Return to the **Sources** tab and select **Add Source**.
5. Choose **GitLab Project**.
6. Enter **Source Name**, **Project**, **Branch**, and **Publishing System**.
   Choose the project in **Project**. Doc Holiday uses the provider token for that project Source.
7. Repeat **Add Source** for each GitLab project that should use the same token.

If another Publishing System fits better, see [Publishing Systems](./d4-publishing-systems.md) for the available **Publishing System** values.

## One project with its own token

Use this path when one project needs its own token.

1. In the **Add Source** sheet with **GitLab Project** selected, use the **Click here ...** helper link to switch to the standalone GitLab form.
2. Enter **Source Name**, **Access Token**, **Project**, **Branch**, and **Publishing System**.
3. Select **Save Changes**.

This form covers one project, and the token stays with that project Source.

## Verify

Open **Sources** and confirm that the Source shows **Healthy**. If it does not, open [Manage connections](./c7-manage-connections.md).

## Next

Continue with [Create your first publication](./b5-create-your-first-publication.md).

---

<!-- doc-holiday-watermark -->
<p align="center">
  <a href="https://doc.holiday">
    <img alt="Doc Holiday logo" src="https://doc.holiday/assets/docs-by-doc-holiday.png" width="200">
  </a>
</p>
<p align="center">Docs authored by <a href="https://doc.holiday">Doc Holiday</a></p>
