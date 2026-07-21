# Manage publications

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

Write access controls who can request work under the Publication. For broader role and access control context, see [User management](/h1-user-management.md).

## Check publication health

1. Open **Status** for a quick health check.
2. Read the **Health:** badge to see the current result.
3. Select **Run Test** after a change or when a fresh check is needed.
4. If the check fails, look for **Health Check Failed** and open **View Troubleshooting Docs** for help.

## Danger Zone

1. Open **Danger Zone** only when the Publication is no longer needed.
2. Select **Delete Publication**.
3. Confirm **Permanently delete this publication.** and then **This cannot be undone.**

```
SCREENSHOT PLACEHOLDER: manage-publications/danger-zone.png
```

Deleting the Publication stops its triggers and new work under that Publication. Repositories and already merged documentation remain untouched.