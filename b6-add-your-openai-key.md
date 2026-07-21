# Add your OpenAI key

Use this page when you already have an OpenAI key and need to finish setup in onboarding or add it later in Settings.

## Who needs this

Use this page for Bring Your Own Key and Open Source Software plans. Enterprise does not use this setup page; see [Billing and plans](/h4-billing-and-plans.md) for plan details.

## Add the key

1. Get an OpenAI key that supports real inference. A key that can only list models fails verification.
2. Add the key in the place that fits your flow.
   - **Onboarding:** On the **"Add your AI provider key"** step, select **"Add Provider Key"** and enter your key.
   - **Settings:** Admins on BYOK and OSS can open **"AI Provider Keys"**, select **"Add AI Provider Key"**, and fill in **"Name"**, **"Provider"**, and **"API Key"**. The **"Provider"** field accepts OpenAI only. Select **"Add Key"** to save it.
3. Doc Holiday verifies the key with a live OpenAI request before it saves anything. If the provider rejects the key, get a new one. If verification cannot complete, try again.
4. Confirm the result. The first OpenAI key you add becomes **"Active"** automatically. In Settings, the key card shows **"Active"** and includes **"Test"**.

```text
SCREENSHOT PLACEHOLDER: add-your-openai-key/keys-page.png
```

## Next

Continue with [AI provider keys](/h3-ai-provider-keys.md) or review [Billing and plans](/h4-billing-and-plans.md).