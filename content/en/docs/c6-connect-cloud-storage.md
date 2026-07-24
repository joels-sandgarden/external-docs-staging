---
title: Connect Cloud Storage
url: "docs/connect-cloud-storage"
description: "Read-only context from S3 or Azure Blob buckets and containers."
---

Cloud storage Sources provide read-only context from cloud storage services. AWS S3 uses the buckets that the credentials can access in a region, and Azure Blob Storage uses a single container. They inform what Doc Holiday writes without starting new work. For the broader Sources model, see [Sources](./c1-sources.md).

## Option A — AWS (S3)

1. Open **Sources** and select **Add Source**.
2. Choose **AWS (S3)**.
3. Enter **Source Name**.
4. Enter **Access Key ID**.
5. Enter **Secret Access Key**.
6. Enter **Region**.
7. Keep **Pause Background Work for Source** selected while configuring the Source.
8. Select **Save Changes**.

## Option B — Azure Blob Storage

1. Open **Sources** and select **Add Source**.
2. Choose **Azure Blob Storage**.
3. Enter **Source Name**.
4. Enter **Account Name**.
5. Enter **Account Key**.
6. Enter **Container Name**.
7. Keep **Pause Background Work for Source** selected while configuring the Source.
8. Select **Save Changes**.

## Verify

Verify that the Source shows **Healthy** on the **Sources** page.

## Next

See [Sources](./c1-sources.md).


<!-- doc-holiday-watermark -->
<p align="center">
  <a href="https://doc.holiday">
    <img alt="Doc Holiday logo" src="https://doc.holiday/assets/docs-by-doc-holiday.png" width="200">
  </a>
</p>
<p align="center">Docs authored by <a href="https://doc.holiday">Doc Holiday</a></p>
