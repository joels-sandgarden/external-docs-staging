---
title: Connect Cloud Storage
url: "docs/connect-cloud-storage"
description: "Read-only context from S3 or Azure Blob buckets and containers."
---

Cloud storage Sources provide read-only context from your storage account — the S3 buckets your credentials can access in a region, or a single Azure Blob container. They inform what Doc Holiday writes without triggering work. For the broader Sources model, see [Sources](./c1-sources.md).

## Option A — AWS (S3)

1. Open **Sources** and select **Add Source**.
2. Choose **AWS (S3)**.
3. Enter **Source Name**.
4. Enter **Access Key ID**.
5. Enter **Secret Access Key**.
6. Enter **Region**.
7. Select **Save Changes**.

## Option B — Azure Blob Storage

1. Open **Sources** and select **Add Source**.
2. Choose **Azure Blob Storage**.
3. Enter **Source Name**.
4. Enter **Account Name**.
5. Enter **Account Key**.
6. Enter **Container Name**.
7. Select **Save Changes**.

## Verify

Verify that the Source shows **Healthy** on the **Sources** page.

## Next

See [Sources](./c1-sources.md).