---
title: Manage Publications
url: "docs/manage-publications"
description: "Edit a Publication, control access, and delete safely."
---

Use this guide when a Publication already exists and needs updates, shared access, health checks, or deletion.

## Edit configuration

1. Open the Publication, then select **Edit**.
2. Update **Name** if the Publication needs a clearer label.
3. Set **Inputs** to the Sources that should feed this Publication.
4. Set **Targets** to the documentation destination.
5. Use **Notify** to choose an optional notification destination.
6. Under **Write:** select **Documentation**, **Release Notes**, and **Changelog** for the content types this Publication should produce.
7. Fill in **Writing Instructions** and **Commit Instructions** to shape the output and commit message format.
8. Save the changes.

## Share access with teammates

1. Open **Manage Access** or **View Access**.
2. Review the **Publication Access** list to see who can work with the Publication.
3. Select **Share Publication** to grant access.
4. Use **Search by name or email...**, then choose **Writer** for teammates who should request work under the Publication or **Reviewer** for review-only access.
5. Use **All access levels** to narrow the list, and select **Revoke access** when someone no longer needs access.

Write access controls who can request work under the Publication. For broader role and access control context, see [User management](./h1-user-management.md).

## Check publication health

1. Use the always-visible **Status** section for a quick health check.
2. Read the **Health:** badge to see the current result.
3. The health check verifies the Publication's connections — the docs repository and each source.
4. Select **Run Test** after a change or when a fresh check is needed.
5. If the check fails, look for **Health Check Failed** and open **View Troubleshooting Docs** for help.

## Danger Zone

1. Open the Publication, then select **Edit**.
2. Scroll to the bottom of the edit form to find **Danger Zone**.
3. The card shows **Delete Publication** with the warnings **Permanently delete this publication.** and **This cannot be undone.**
4. Select **Delete Publication**.
5. In the dialog titled **Delete Publication**, read **Are you sure you want to delete this publication?** and confirm with **Delete this publication**.

```
SCREENSHOT PLACEHOLDER: manage-publications/danger-zone.png
```

Deleting the Publication stops its triggers and new work under that Publication. Repositories and already merged documentation remain untouched.