# Connect Confluence and Jira

Use this guide when Doc Holiday needs Confluence for read-only context or Jira for work that starts from Publication triggers. For a broader Sources overview, see [Sources](/c1-sources.md).

## Confluence

Confluence adds read-only context and never starts work.

1. Open **Sources**, select **Add Source**, and choose **Confluence**.
2. Enter **Source Name**, **URL**, **Username**, and **API Token**.
3. Select **Save Changes**.

## Jira app-backed setup

Note: Both Jira paths use the same Publication triggers, **Send to Doc** and **Issue status changes**. Configure those triggers on the Publication, then open [Configure triggers](/d2-configure-triggers.md).

Use the app-backed path when Jira connects through an **Atlassian Application**.

1. Open **Providers**, select **Add Provider**, and choose **Atlassian Application**.
2. Enter **Atlassian Site URL** and select **Register Site**.
3. Select **Install Atlassian Application**.
4. If another Atlassian Site Admin must complete installation, copy the read-only installation link shown in the form and share it with that admin.
5. Open **Sources**, select **Add Source**, and choose **Jira Project**.
6. Complete **Source Name** and **Jira Project**. When more than one application exists, the form also shows the **Atlassian Application** selector.
7. Select **Save Changes**.

## Jira token-based setup

Use the token-based path when Jira connects without an **Atlassian Application**.

1. Open **Sources**, select **Add Source**, and choose **Jira Read-Only**.
2. Enter **Source Name**, **URL**, **Email Address**, **API Token**, and **Project Key**.
3. Select **Save Changes**.

## Verify

Open **Sources** and confirm the Source status reads **Healthy**.

## Next

See [Sources](/c1-sources.md) or [Configure triggers](/d2-configure-triggers.md).