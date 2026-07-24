---
title: Create Your First Publication
url: "docs/create-your-first-publication"
description: "Set up your first Publication: Sources, docs destination, output types."
---

A Publication is the defined set of documentation Doc Holiday keeps current over time; see [Publications](./d1-publications.md). This guide walks through the first setup in the app and shows how to choose Sources, one docs destination, and the output types that belong in the first Publication.

## Prerequisites

- At least one connected git repository Source; see [Connect GitHub](./b2-connect-github.md).
- One docs destination repository. A separate repository for docs is normal and recommended.
- An admin role. Only admins can add a Publication.

![The Publication form with Inputs, Targets, and Write sections](/screenshots/quickstart/publication-form.png)

1. Open **Publications** and select **Add Publication**. The **Create Publication** panel opens.
2. Enter a **Name** that makes the Publication easy to recognize later.
3. Under **Inputs**, choose the Sources this Publication should read from.
4. Under **Targets**, choose the docs destination.
5. Under **Write**, turn on **Documentation** only. Leave **Release Notes** and **Changelog** off for the first Publication. See [Output types](./d3-output-types.md) for the full set of options.
6. Leave **Commit Instructions** and **Writing Instructions** at their defaults for now.
7. Below **Inputs**, the form shows trigger settings under **Add Triggering Event**. Leave them empty for now; see [Configure triggers](./d2-configure-triggers.md). Finish by selecting **Save Changes**.

## Verify

Open the publication details view and confirm the **Status** section shows **Healthy**. Select **Run Test** to check it again.

## Next

Next: [Request work in the app](./f2-request-work-in-the-app.md).