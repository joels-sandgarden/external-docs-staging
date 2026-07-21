# Audit log

## Where it lives

Open **Audit Log** at `/logs` to see who changed what. Only admins can access this page.

## What each entry shows

The table shows **EVENT**, **TARGET**, **TIME**, and **USER**. Select a row to open a side sheet with **Source:**, **Source Type:**, **Publication:**, **API Key**, **Event:**, **Time:**, and **User:**. When present, the sheet also shows the summary and delta text.

The row list and the side sheet use these event names: **Created**, **Updated**, **Deleted**, **Source Healthcheck**, and **Publication Healthcheck**.

## Event filters

| Filter | Shows |
| --- | --- |
| **All Entries** | Every audit entry. |
| **Creation Events** | Created entries. |
| **Deletion Events** | Deleted entries. |
| **Update Events** | Updated entries. |
| **Source Healthcheck** | Source healthcheck entries. |
| **Publication Healthcheck** | Publication healthcheck entries. |

Audit Log also includes system-generated assessment entries for writing work.

## Next

Next: [Work History](/work-history)