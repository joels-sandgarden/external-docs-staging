---
title: Add Your OpenAI Key
url: "docs/add-your-openai-key"
description: "Add and test the OpenAI key Doc Holiday uses for your organization."
---

Use this page when you already have an OpenAI key and need to finish setup in onboarding or add it later in Settings.

## Who needs this

Use this page for the Bring Your Own Key and Open Source plans. Enterprise does not use this setup page; see [Billing and plans](./h4-billing-and-plans.md) for plan details.

Only OpenAI keys are accepted.

## Add the key

1. Get an OpenAI key that supports real inference. A key that can only list models fails verification.
2. Add the key in the place that fits your flow.
   - **Onboarding:** On the **"Add your AI provider key"** step, enter your key and select **"Add Provider Key"**.
   - **Settings:** Admins on BYOK and OSS can open **"AI Provider Keys"**, select **"Add AI Provider Key"**, and fill in **"Name"**, **"Provider"**, and **"API Key"**. The **"Provider"** field accepts OpenAI only. Select **"Add Key"** to save it.
3. Doc Holiday verifies the key with a live OpenAI request before it saves anything. If Doc Holiday returns "the provider rejected this api key", get a new key. If Doc Holiday returns "could not verify the api key, try again", the check could not complete, so try again.
4. Confirm the key saved successfully. The first OpenAI key added becomes **Active** automatically.

![The AI Provider Keys page with two keys: one Active and Healthy, one Unhealthy](/screenshots/add-your-openai-key/keys-page.png)

## Verify

The key appears with status **Active**, and **Test** in the key's menu confirms it works.

## Next

Continue with [AI provider keys](./h3-ai-provider-keys.md) or review [Billing and plans](./h4-billing-and-plans.md).