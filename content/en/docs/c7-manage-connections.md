---
title: Manage Connections
url: "docs/manage-connections"
description: "Check health, restore access, edit details, or remove a Source or provider."
---

Keep Sources and providers healthy, restore access when a Source breaks, edit Source details, and remove Sources or providers only after dependent Publications are updated. This guide covers the routine checks and fixes that keep connected Sources ready for Doc Holiday to read.

![The Sources list with a health badge on each connection](/screenshots/manage-connections/health-list.png)

## Check health

1. Open **Sources**.
2. Find the Source row.
3. Read the badge in the status column.
4. Use the badge text as a quick check:
   - **Healthy** means Doc Holiday can read the Source.
   - **Unhealthy** means Doc Holiday stops reading it until the problem clears.
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
5. If a GitHub provider still fails, open **Manage GitHub Application** and complete that setup again.
6. Return to **Sources** and confirm the status badge reads **Healthy**.

## Edit a Source

1. Open the Source in **Sources** or the provider in **Providers**.
2. Select **Edit**.
3. Change **Source Name** to rename a Source.
4. Change **Branch** to point a repository Source at a different branch.
5. The sheet title reads **Update Source** or **Update Provider**.
6. Select **Save Changes** to keep the updates. Select **Cancel** or **Close** to leave the current values unchanged.

## Delete a Source

1. Update any Publication that still points at the Source before deleting it.
2. Remove dependent Sources before deleting a provider.
3. Select **Delete** in the row's menu.
4. Review the warning, then select **Delete this source** or **Delete this provider** to confirm.
5. Doc Holiday removes provider-side setup it created, such as webhooks or a GitHub App installation.
6. The repository stays in place, and already merged documentation remains unchanged.

Next: [Sources](./c1-sources.md).
