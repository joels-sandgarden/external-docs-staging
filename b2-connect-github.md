# Connect GitHub to Doc Holiday

GitHub setup in Doc Holiday uses two steps. First, connect the organization-wide **GitHub Application**. Then add one **GitHub Repository** Source for each repository Doc Holiday should read or write. That split keeps the shared GitHub app install separate from the per-repository setup, and it gives the **Connections** page a clear health signal for every Source.

## Install the GitHub App

1. Select **Install GitHub App** to start the organization install flow.
2. If the current GitHub account cannot finish installation, open **Need an admin to install the GitHub App?** and then select **Click here to create a link.** Share that link with a GitHub administrator so the install can finish in the right organization.

``` 
SCREENSHOT PLACEHOLDER: connect-github/app-install.png
```

After the app is installed, Doc Holiday can create repository Sources under it.

## Add repository connections

1. In the onboarding repository picker, select the repositories you want Doc Holiday to use and select **Add Sources**. Doc Holiday creates one Source for each repository you select.
2. If the single Source form appears instead, enter **Source Name**, **Repository**, and **Branch**. The branch picker preselects the repository default branch and marks it **(default)**.
3. If the form shows the missing-provider alert, install the GitHub App first and return to repository setup.

``` 
SCREENSHOT PLACEHOLDER: connect-github/repo-connection-form.png
```

The repository picker keeps setup simple when several repositories belong to the same organization. The single Source form helps when only one repository needs to connect.

### Option B: Use a Personal Access Token

Use this option when the GitHub App cannot be installed. Choose the helper link that says **Click here** to connect with a Personal Access Token (PAT) instead. Then enter **Source Name**, **Personal Access Token**, **Repository**, and **Branch**. The opposite switch on that form says **Click here** to connect with a GitHub application instead.

This path works for repositories that still need access without an app-based install. It uses the same repository and branch choices, but it asks for a token instead of an app connection.

## Verify

1. Open **Connections** and find the new Source row.
2. Confirm that the health badge shows **Healthy**.
3. If the badge shows **Unhealthy**, open [/c7-manage-connections.md](/c7-manage-connections.md) and check the Source setup again.

## Next

Continue to [/b5-create-your-first-publication.md](/b5-create-your-first-publication.md) to create the Publication that uses these Sources.