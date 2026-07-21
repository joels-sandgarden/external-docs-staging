# Connect Confluence and Jira


Use this guide when you want Doc Holiday to read Confluence for context and connect Jira for work started by triggers. Confluence stays read only. Jira can use the app backed path or the read only path.

## Confluence

Confluence gives Doc Holiday context for writing. It never starts work on its own.

1. In **Sources**, choose `Confluence`.
2. Enter **Source Name**.
3. If the control appears, turn on **Pause Background Work for Source** to pause updates.
4. Enter **URL**, **Username**, and **API Token**.
5. Save the Source.

## Jira

Use the `Atlassian Application` + `Jira Project` path when you can install the app and Jira should take part in work started by triggers; use `Jira Read-Only` when a token based setup fits better.

### App backed path

1. In **Sources**, choose `Atlassian Application`.
2. Enter **Provider Name**.
3. Enter **Atlassian Site URL**.
4. Choose **Register Site**.
5. Finish setup with **Install Atlassian Application**.
6. Share the installation link with **Share Installation Link** if another site admin needs to complete the install.
7. Add a new Source and choose `Jira Project`.
8. Enter **Source Name**.
9. Select **Atlassian Application**, then choose the app from **Select an Atlassian Application...**.
10. Select **Jira Project** by searching with **Search projects...** and choosing **Select a project...**.
11. If Jira should trigger work, set up the trigger on the Publication in [Configure triggers](./d2-configure-triggers.md) and use `Send to Doc` or issue status changes.

### Read only path

1. In **Sources**, choose `Jira Read-Only`.
2. Enter **Source Name**.
3. If the control appears, turn on **Pause Background Work for Source** to pause updates.
4. Enter **URL**, **Email Address**, **API Token**, and **Project Key**.
5. Save the Source.

## Verify

Verify that both sources show `Healthy` on the `Sources` page.

## Next

See [Sources](./c1-sources.md).
