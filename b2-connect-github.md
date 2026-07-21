# Connect GitHub to Doc Holiday

GitHub setup in Doc Holiday uses two steps. First, connect the organization-wide **GitHub Application**. Then add one **GitHub Repository** Source for each repository Doc Holiday should read or write. Use this page when you set up GitHub for the first time or when you add another repository to an existing organization install.

That split keeps the shared GitHub app install separate from the per-repository setup, and it gives the **Connections** page a clear health signal for every Source. It also lets one organization install support several repositories without repeating the app step each time.

Start with the organization install only once. After that, each repository choice stays local to the Source you are creating, so the setup stays easy to review later.

When a team shares one GitHub organization, that pattern keeps the admin work small and makes it easier to see which repositories belong to Doc Holiday.

## Install the GitHub App

1. Select **Install GitHub App** to start the organization install flow.
2. If the current GitHub account cannot finish installation, open **Need an admin to install the GitHub App?** and then select **Click here to create a link.** Share that link with a GitHub administrator so the install can finish in the right organization. That path matters when your GitHub account cannot grant organization access on its own.
3. After the install completes, return to Doc Holiday and continue with repository setup. The organization app install only needs to happen once.

If your organization already has the app, you can move straight to repository setup. Otherwise, this step gives Doc Holiday the shared access it needs before you pick any repositories.

If the admin link is the only path available, the administrator can finish the install from GitHub without changing the repository plan in Doc Holiday.

```
SCREENSHOT PLACEHOLDER: connect-github/app-install.png
```

After the app is installed, Doc Holiday can create repository Sources under it without asking for another organization level install.

## Add repository connections

1. In the onboarding repository picker, select the repositories you want Doc Holiday to use and select **Add Sources**. Doc Holiday creates one Source for each repository you select, so a single install can cover many repositories.
2. If the single Source form appears instead, enter **Source Name**, **Repository**, and **Branch**. The branch picker preselects the repository default branch and marks it **(default)**, which helps you confirm the branch Doc Holiday will follow.
3. If the form shows the missing-provider alert, install the GitHub App first and return to repository setup. That alert tells you the repository Source cannot finish until the organization app exists.
4. Use the repository picker when you want to add several repositories at once. Use the single Source form when you only need one repository entry or when you want to review each field separately.

The onboarding picker works well when a whole team or product area belongs in the same setup. The single Source form works well when one repository needs careful review before you save it.

That means you can add several repositories now and leave the rest for later, or focus on one repository when you want a smaller change.

```
SCREENSHOT PLACEHOLDER: connect-github/repo-connection-form.png
```

The repository picker keeps setup simple when several repositories belong to the same organization. The single Source form helps when only one repository needs to connect, or when you want to confirm the branch before you save.

### Option B: Use a Personal Access Token

Use this option when the GitHub App cannot be installed. Choose the helper link that says **Click here** to connect with a Personal Access Token (PAT) instead. Then enter **Source Name**, **Personal Access Token**, **Repository**, and **Branch**. The opposite switch on that form says **Click here** to connect with a GitHub application instead.

This path works for repositories that still need access without an app based install. It uses the same repository and branch choices, but it asks for a token instead of an app connection. Pick it when an organization policy, a temporary access limit, or a missing admin blocks the app install.

Keep the token private and reuse the same repository and branch values you would choose for an app connection. The token option changes the way Doc Holiday authenticates, but it does not change what repository Source you create.

Use it for temporary access during onboarding or when policy blocks an app install. The resulting Source still points at one repository and one branch.

## Verify

1. Open **Connections** and find the new Source row.
2. Confirm that the health badge shows **Healthy**. That result tells you Doc Holiday can reach the Source and work with it normally.
3. If the badge shows **Unhealthy**, open [/c7-manage-connections.md](/c7-manage-connections.md) and check the Source setup again. Fix the connection before you move on.

Healthy means the Source is ready for normal use. Unhealthy means Doc Holiday needs another look at the setup before you continue.

A healthy row confirms the repository and branch choices worked as expected, so you can move on with confidence.

## Next

Continue to [/b5-create-your-first-publication.md](/b5-create-your-first-publication.md) to create the Publication that uses these Sources. That page finishes the setup by pointing your documentation project at the Sources you just connected, so Doc Holiday can start working against real repository content and keep the page current as repositories change.