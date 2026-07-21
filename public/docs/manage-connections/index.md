# Manage Connections


Keep your Sources healthy, fix a broken Source, edit details, or remove a Source or provider when it no longer belongs in Doc Holiday. Use this guide after setup when you need to check health, restore access, edit details, or remove a Source or provider.

![The Sources list with a health badge on each connection](/screenshots/manage-connections/health-list.png)

## Check health

1. Open **Sources**.
2. Find the row for the Source.
3. Read the badge in the status column.
4. Use the badge text as your quick check:
   - **Healthy** means Doc Holiday can read the Source.
   - **Unhealthy** means Doc Holiday skips it until you fix the problem.
   - **Checking...** means Doc Holiday is still checking it.
5. Doc Holiday reads connected Sources regularly. When a Source stays **Unhealthy**, its information can go stale while other Sources keep updating.

## Fix an unhealthy Source

1. Open the Source in **Sources** or the provider in **Providers**.
2. Select **Edit**.
3. Check these common causes:
   - Credentials expired or were revoked.
   - A provider app no longer exists in the workspace.
   - The repository or project moved, or someone deleted it.
4. Update the visible fields in the sheet, then select **Save Changes**.
5. If you need to reinstall a GitHub App on the provider side, open **Manage GitHub Application** and complete that setup again.
6. Return to **Sources** and confirm the status badge reads **Healthy**.

## Edit a Source

1. Open the Source in **Sources** or the provider in **Providers**.
2. Select **Edit**.
3. Change **Source Name** when you want to rename a Source.
4. Change **Branch** when you want Doc Holiday to track a different branch for a repository Source.
5. The sheet title reads **Update Source** or **Update Provider**.
6. Select **Save Changes** when you finish. Select **Cancel** or **Close** to leave the current values unchanged.

## Delete a Source

1. Update any Publication that still points at the Source before you delete it.
2. If you delete a provider, remove its dependent Sources first.
3. Select **Delete** in the row's menu.
4. Review the warning, then select **Delete this source** (or **Delete this provider**) to confirm.
5. Doc Holiday removes provider-side setup it created, such as webhooks or a GitHub App installation.
6. The repository itself stays in place, and already merged documentation remains unchanged.

Next: [Sources](./c1-sources.md).
