---
title: AI Provider Keys
url: "docs/ai-provider-keys"
description: "Manage the AI provider keys Doc Holiday uses for writing runs."
---

The page helps admins manage the AI provider keys that power an organization’s writing runs. The page title is **AI Provider Keys**. Supported providers include OpenAI, Groq, and Cerebras. The page applies to organizations on the Bring Your Own Key and Open Source plans. Bring Your Own Key organizations finish billing during onboarding, then add provider keys here before they start new work. Enterprise customers manage inference through the account team; see [Billing and plans](./h4-billing-and-plans.md).

![The AI Provider Keys page with two keys: one Active and Healthy, one Unhealthy](/screenshots/add-your-openai-key/keys-page.png)

If no keys exist, the page shows **No AI Provider Keys yet**.

## Add a key

1. Admins select **Add AI Provider Key**.
2. In the dialog, admins enter **Name**, choose one of the supported providers in **Provider**, and paste the **API Key**.
3. Admins select **Add Key**. **Cancel** closes the dialog without saving.
   Doc Holiday sends a live verification request before it saves the key. If the provider returns an error, the page shows that provider error and keeps the key out of service.

## Manage active and failover keys

The active key card shows the **Active** badge. Every key card menu includes **Test** and **Delete**. Inactive key card menus also include **Set Active**.

1. The first valid key from any supported provider becomes active automatically.
2. Admins open a key card and select **Set Active** to move the **Active** badge to that key. Doc Holiday keeps the previous active key as failover.
3. If the active key stops working, Doc Holiday tries another stored key during the request. If every key fails, the request fails and the page shows the provider problem.

Doc Holiday only uses keys that the organization has added. It never falls back to any other key.

## Rotate a key

1. Admins add the new key.
2. Admins select **Set Active** on the new key.
3. Admins delete the old key.

Key changes apply immediately, including to work that starts after the change.

## Test and delete a key

1. Admins open the overflow menu on any key card and select **Test** when needed.
2. The result shows **Key is valid** when the key works and **Key test failed** when it does not. If the provider returns an error, the message appears in the page results.
3. Admins open the overflow menu again and select **Delete** to remove a key.
4. Admins confirm **Delete AI provider key?**. The dialog also offers **Cancel**. Doc Holiday removes the stored key from the organization.

## Next

- Setup begins in [Add your AI provider key](./b6-add-your-openai-key.md).
- The [Billing and plans](./h4-billing-and-plans.md) page covers plan coverage and Enterprise billing.