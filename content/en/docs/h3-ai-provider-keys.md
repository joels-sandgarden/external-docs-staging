---
title: AI Provider Keys
url: "docs/ai-provider-keys"
description: "Manage provider-scoped AI provider keys, validation, failover, and rotation."
---

Use this page to manage the AI provider keys that power an organization’s writing runs. The app page title is **AI Provider Keys**. The page shows the providers that the organization supports, including OpenAI, Anthropic, Gemini, Groq, and Cerebras. Each key belongs to the provider selected when it is added, and Doc Holiday handles active and failover behavior within that provider. The page applies to organizations on the Bring Your Own Key and Open Source plans. See [Billing and plans](./h4-billing-and-plans.md) for plan coverage.

![The AI Provider Keys page with two keys: one Active and Healthy, one Unhealthy](/screenshots/add-your-openai-key/keys-page.png)

If no keys exist, the page shows **No AI Provider Keys yet**.

## Add a key

1. Select **Add AI Provider Key**.
2. In the dialog, enter **Name**, choose **Provider** from the supported list, and paste the **API Key** for that provider.
3. Select **Add Key**. Use **Cancel** to close the dialog without saving.
   Doc Holiday tests the key for the selected provider before it saves it, and it rejects keys that cannot run inference.

## Manage active and failover keys

The active key card shows the **Active** badge. Every key card menu includes **Test** and **Delete**. Inactive key card menus also include **Set Active**. Doc Holiday tracks active and failover keys separately for each provider.

1. The first key for a provider becomes active automatically.
2. Open a key card and select **Set Active** to move the **Active** badge to that key. Doc Holiday marks the previous active key for that provider as failover.
3. If the active key for a provider fails, Doc Holiday tries another stored key for the same provider during the same request. If every key for that provider fails, the work errors.

Doc Holiday never uses a key from a different provider.

## Rotate a key

1. Add a replacement key for the same provider.
2. Select **Set Active** on it.
3. Delete the old key.

Doc Holiday applies key changes immediately, including to work already in flight.

## Test and delete a key

1. Open the overflow menu on any key card and select **Test** when needed.
2. Check the result. Doc Holiday shows **Key is valid** when the key passes and **Key test failed** when it does not.
3. Open the overflow menu again and select **Delete** to remove a key.
4. Confirm **Delete AI provider key?**. The dialog also offers **Cancel**. Doc Holiday deletes the stored key and removes the secret.

## Next

- Start setup in [Add a key](./b6-add-your-openai-key.md).
- Review [Billing and plans](./h4-billing-and-plans.md) for plan coverage and Enterprise inference.