---
title: AI Provider Keys
url: "docs/ai-provider-keys"
description: "Add, test, and rotate the keys Doc Holiday uses; active-key behavior."
---

Use this page to manage the AI provider keys that power an organization’s writing runs. The app page title is **AI Provider Keys**. Doc Holiday supports provider-managed keys for OpenAI, Anthropic, Gemini, Groq, and Cerebras. The page applies to organizations on the Bring Your Own Key and Open Source plans. Doc Holiday manages Enterprise inference; see [Billing and plans](./h4-billing-and-plans.md).

![The AI Provider Keys page with two keys: one Active and Healthy, one Unhealthy](/screenshots/add-your-openai-key/keys-page.png)

If no keys exist, the page shows **No AI Provider Keys yet**.

## Add a key

1. Select **Add AI Provider Key**.
2. In the dialog, enter **Name**, choose a **Provider**, and paste the **API Key** for OpenAI, Anthropic, Gemini, Groq, or Cerebras.
3. Select **Add Key**. Use **Cancel** to close the dialog without saving.
   Doc Holiday sends a real request to the selected provider before it saves the key, and it rejects keys that cannot run inference.

Provider-specific secrets or deployment settings must exist wherever the selected provider requires them. Gemini uses `GEMINI_API_KEY`, Groq uses `GROQ_API_KEY`, and Cerebras uses `CEREBRAS_API_KEY`.

## Manage active and failover keys

The active key card shows the **Active** badge. Every key card menu includes **Test** and **Delete**. Inactive key card menus also include **Set Active**.

1. The first key for a provider becomes active automatically.
2. Open a key card and select **Set Active** to move the active badge to that key. Doc Holiday demotes the previous active key to failover.
3. If the selected provider rejects the active key, Doc Holiday fails over to another stored key for the same provider within the same request. It never switches to a different provider behind the scenes. If every key fails, the work errors.

Doc Holiday only uses keys your organization has added.

## Rotate a key

1. Add the new key.
2. Select **Set Active** on it.
3. Delete the old key.

Key changes apply immediately, even to work already in flight.

## Test and delete a key

1. Open the overflow menu on any key card and select **Test** when needed.
2. Check the result. Doc Holiday shows **Key is valid** when the key works and **Key test failed** when it does not.
3. Open the overflow menu again and select **Delete** to remove a key.
4. Confirm **Delete AI provider key?**. The dialog also offers **Cancel**. Doc Holiday deletes the stored key and scrubs the secret.

## Next

- Review [Billing and plans](./h4-billing-and-plans.md) for plan coverage and Enterprise inference.
- See [Security and data handling](./h5-security-and-data-handling.md) for key handling and inference behavior.

---

<!-- doc-holiday-watermark -->
<p align="center">
  <a href="https://doc.holiday">
    <img alt="Doc Holiday logo" src="https://doc.holiday/assets/docs-by-doc-holiday.png" width="200">
  </a>
</p>
<p align="center">Docs authored by <a href="https://doc.holiday">Doc Holiday</a></p>
