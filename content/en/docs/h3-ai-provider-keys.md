---
title: AI Provider Keys
url: "docs/ai-provider-keys"
description: "Add, test, and rotate the keys Doc Holiday uses; active-key behavior."
---

Use this page to manage the OpenAI keys that power an organization’s writing runs. The app page title is **AI Provider Keys**. OpenAI is the only supported provider on this page. The page applies to organizations on the Bring Your Own Key and Open Source plans. Doc Holiday manages enterprise inference; see [Billing and plans](./h4-billing-and-plans.md).

```
SCREENSHOT PLACEHOLDER: add-your-openai-key/keys-page.png
```

If no keys exist, the page shows **No AI Provider Keys yet**.

## Add a key

1. Select **Add AI Provider Key**.
2. In the dialog, enter **Name**, choose **Provider** as **OpenAI**, and paste the **API Key**.
3. Select **Add Key**. Use **Cancel** to close the dialog without saving.
   Doc Holiday sends a real OpenAI verification call before it saves the key, and it rejects keys that cannot run inference.

## Manage active and failover keys

The active key card shows the **Active** badge. Every key card menu includes **Test** and **Delete**. Inactive key card menus also include **Set Active**.

1. The first OpenAI key becomes active automatically.
2. Open a key card and select **Set Active** to move the active badge to that key. Doc Holiday demotes the previous active key to failover.
3. If your provider rejects the active key, Doc Holiday fails over to another stored key within the same request. If every key fails, the work errors.

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
4. Confirm **Delete AI provider key?**. The dialog also offers **Cancel**. Doc Holiday deletes the stored key and scrubs the secret.

## Next

- Start setup in [Add your OpenAI key](./b6-add-your-openai-key.md).
- Review [Billing and plans](./h4-billing-and-plans.md) for plan coverage and Enterprise inference.