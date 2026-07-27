---
title: AI Provider Keys
url: "docs/ai-provider-keys"
description: "Add, test, and manage the AI provider keys Doc Holiday uses."
---

Use this page to manage the AI provider keys for an organization. The app page title is **AI Provider Keys**. Doc Holiday supports OpenAI, Anthropic, and Gemini on this page. The page applies to organizations on the Bring Your Own Key and Open Source plans. Enterprise uses a separate billing setup; see [Billing and plans](./h4-billing-and-plans.md).

![The AI Provider Keys page with two keys: one Active and Healthy, one Unhealthy](/screenshots/add-your-openai-key/keys-page.png)

If no keys exist, the page shows **No AI Provider Keys yet**.

## Add a key

1. Select **Add AI Provider Key**.
2. In the dialog, choose a provider from the list, then enter **Name** and the **API Key**. The dialog shows provider specific icons, hints, and placeholder text for each provider.
3. Select **Add Key**. Use **Cancel** to close the dialog without saving.
   Doc Holiday checks the key with the selected provider before it saves the key.

## Manage active and failover keys

Each provider has its own active key. The active key card shows the **Active** badge. Every key card menu includes **Test** and **Delete**. Inactive key card menus also include **Set Active**.

1. The first saved key for a provider becomes active automatically.
2. Open a key card and select **Set Active** to move the active badge to that key for the same provider.
3. If the active key fails, Doc Holiday uses another saved key for that provider. If every key fails, the work errors.

Doc Holiday only ever uses keys your organization has added — there is no fallback to any other key.

## Rotate a key

1. Add the new key.
2. Select **Set Active** on it.
3. Delete the old key.

Key changes apply immediately, even to work already in flight.

## Test and delete a key

1. Open the overflow menu on any key card and select **Test** when needed.
2. Check the result. Doc Holiday shows **Key is valid** when the key works and **Key test failed** when it does not.
3. Open the overflow menu again and select **Delete** to remove a key.
4. Confirm **Delete AI provider key?**. The dialog also offers **Cancel**. Doc Holiday removes the stored key.

## Next

- Start setup in [Add Your AI Provider Key](./b6-add-your-openai-key.md).
- Review [Billing and plans](./h4-billing-and-plans.md) for plan coverage and Enterprise provider access.