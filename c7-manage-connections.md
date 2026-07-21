# Manage connections

Keep your Sources healthy, fix a broken connection, or remove a Source or provider when it no longer belongs in Doc Holiday. Use this guide after setup when you need to check status, repair access, or make routine changes.

```
SCREENSHOT PLACEHOLDER: manage-connections/health-list.png
```

## Check health

1. Open **Sources**.
2. Find the row for the Source.
3. Read the badge in the status column.
4. Use the badge text as your quick check:
   - **Healthy** means Doc Holiday can read the Source.
   - **Unhealthy** means Doc Holiday skips it until you fix the problem.
   - **Checking...** means Doc Holiday is still checking it.
5. Doc Holiday re-reads connected sources regularly. When a Source stays **Unhealthy**, its information can go stale while other Sources keep updating.

## Fix an unhealthy connection

1. Open the Source or provider in **Sources** or **Providers**.
2. Select **Edit**.
3. Look for the common causes:
   - Credentials expired or were revoked.
   - A provider app no longer exists in the workspace.
   - The repository or project moved, or someone deleted it.
4. Update the visible fields in the sheet, then select **Save Changes**.
5. If you need to reinstall a GitHub App on the provider side, open **Manage GitHub Application** and complete that setup again.
6. Return to **Sources** and confirm the status badge reads **Healthy**.

## Edit a connection

1. Open the Source or provider in **Sources** or **Providers**.
2. Select **Edit**.
3. Change **Source Name** when you want to rename a Source.
4. Change **Branch** when you want Doc Holiday to track a different branch for a repository Source.
5. Use the title at the top of the sheet as your cue. It reads **Update Source** or **Update Provider**.
6. Select **Save Changes** when you finish. Select **Cancel** or **Close** if you want to leave the current values unchanged.

## Delete a connection

1. Update any Publication that still points at the Source before you delete it.
2. If you delete a provider, move the Sources that depend on it first.
3. Open the Source or provider.
4. Select **Delete this source** or **Delete this provider**.
5. Review the warning, then confirm the delete.
6. Doc Holiday removes provider-side setup it created, such as webhooks or a GitHub App installation, when that setup applies.
7. The repository itself stays in place, and already merged documentation stays unchanged.

Next: [Sources](/c1-sources.md).