# Configure triggers

This guide explains how to configure automatic trigger behavior for an existing Publication. See [Concepts](/a3-concepts.md) for the definitions of Publication and Source. Use it when a Publication should react to new activity in one of its connected Sources.

## Where trigger settings live

Each Source in a Publication has its own trigger settings on the Publication form. Open the Publication, go to **Inputs**, and use **React to** to add triggers for a selected Source. The **Add Triggering Event** control only shows Sources that appear in **Inputs** and can emit at least one trigger event.

```
SCREENSHOT PLACEHOLDER: configure-triggers/trigger-config.png
```

## Trigger events by Source type

| Event concept | On-screen label | Supported Sources |
| --- | --- | --- |
| Merged pull requests | GitHub-only Sources show **Pull Requests**, GitLab-only Sources show **Merge Requests**, and mixed GitHub and GitLab selections show **Pull / Merge Requests** | GitHub repository, GitHub access-token, GitLab, GitLab project, Bitbucket repository, Bitbucket project |
| New issues | **New Issues** | GitHub repository, GitHub access-token, GitLab, GitLab project, Linear |
| Issue comments | **Issue Comments** | GitHub repository, GitHub access-token, GitLab, GitLab project, Bitbucket repository, Bitbucket project, Linear |
| Releases | **Releases** | GitHub repository, GitHub access-token, GitLab, GitLab project |
| Send to Doc | **Send to Doc** | Jira project, Atlassian Forge Jira project |
| Issue status changes | **Issue status changes to:** and **Select statuses...** | Jira project, Atlassian Forge Jira project |

## Add and remove triggers

1. Open the Publication you want to update.
2. Go to **Inputs**.
3. Select **Add Triggering Event**.
4. Choose a Source from the list.
5. Select the triggers that Source supports. For Jira Sources, choose one or more statuses with **Select statuses...**.
6. Save the Publication.

To remove a trigger setup, use the trash button on the Source card. Removing the Source from **Inputs** also clears that Source’s trigger settings.

> Note: Manual requests from git or from the app still work even when no triggers are configured. See [Request work in git](/f1-request-work-in-git.md) and [Request work in the app](/f2-request-work-in-the-app.md).

> Note: Doc Holiday does not offer a scheduled or cron trigger. Use [GitHub Action](/g1-github-action.md) for scheduled or release-driven runs.

## Verify

Merge a small test pull request, then open [Work History](/f4-work-history.md) and confirm that a new entry appears for the Publication.