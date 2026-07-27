---
title: Add Your AI Provider Key
url: "docs/add-your-openai-key"
description: "Add and test the AI provider key Doc Holiday uses for your organization."
---

This page covers supported AI provider keys for onboarding and Settings setup.

## Who needs this

This page applies to the Bring Your Own Key and Open Source plans. Enterprise does not use this setup page; see [Billing and plans](./h4-billing-and-plans.md) for plan details.

The Provider field lists the supported providers.

## Add the key

1. Get a key from a supported provider. A key that can only list models fails verification.
2. Add the key through the setup path that matches the current flow.
   - **Onboarding:** On the **"Add your AI provider key"** step, enter the key, select a supported provider in **"Provider"**, and select **"Add Provider Key"**.
   - **Settings:** Admins on BYOK and OSS can open **"AI Provider Keys"**, select **"Add AI Provider Key"**, and fill in **"Name"**, **"Provider"**, and **"API Key"**. Select **"Add Key"** to save it.
3. Doc Holiday verifies the key with a live request to the selected provider before it saves anything. If Doc Holiday returns "the provider rejected this api key", get a new key. If Doc Holiday returns "could not verify the api key, try again", the check could not complete, so try again.
4. Confirm the key saved successfully. The first key added becomes **Active** automatically.

![The AI Provider Keys page with two keys: one Active and Healthy, one Unhealthy](/screenshots/add-your-openai-key/keys-page.png)

## Verify

The key appears with status **Active**, and **Test** in the key's menu confirms it works.

## Next

See [AI provider keys](./h3-ai-provider-keys.md) for the key reference and [Billing and plans](./h4-billing-and-plans.md) for plan coverage.