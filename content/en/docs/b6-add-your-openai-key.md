---
title: Add Your AI Provider Key
url: "docs/add-your-openai-key"
description: "Add and test the AI provider key Doc Holiday uses for your organization."
---

Use this page when onboarding or Settings asks for an AI provider key. Select the provider from the supported list, then enter the matching key.

## Who needs this

Use this page for the Bring Your Own Key and Open Source plans. Enterprise does not use this setup page; see [Billing and plans](./h4-billing-and-plans.md) for plan details.


## Add the key

1. Get a key from a supported provider that can run real inference. A key that can only list models fails verification.
2. Add the key in the place that fits the flow.
   - **Onboarding:** On the **"Add your AI provider key"** step, select the provider and enter the key.
   - **Settings:** Admins on BYOK and OSS can open **"AI Provider Keys"**, select **"Add AI Provider Key"**, and fill in **"Name"**, **"Provider"**, and **"API Key"**. The **"Provider"** field lists the supported providers.
3. Doc Holiday verifies the key with a live provider request before it saves anything. If Doc Holiday returns "the provider rejected this API key", get a new key. If Doc Holiday returns "could not verify the API key, try again", the check could not complete, so try again.
4. Confirm the key saved successfully. The first saved key for that provider becomes **Active** automatically.

![The AI Provider Keys page with two keys: one Active and Healthy, one Unhealthy](/screenshots/add-your-openai-key/keys-page.png)

## Verify

The key appears with status **Active**, and **Test** in the key's menu confirms it works.

## Next

Continue with [AI provider keys](./h3-ai-provider-keys.md) or review [Billing and plans](./h4-billing-and-plans.md).