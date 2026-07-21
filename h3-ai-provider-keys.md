# AI Provider Keys

Use this page to manage the OpenAI keys that power an organization’s writing runs. The app page title is **AI Provider Keys**. OpenAI is the only supported provider on this page. The page applies to organizations on Bring Your Own Key and Open Source Software plans. Doc Holiday manages enterprise inference; see [Billing and plans](/h4-billing-and-plans.md).

SCREENSHOT PLACEHOLDER: add-your-openai-key/keys-page.png

When no keys exist, the page shows **No AI Provider Keys yet**.

## Add a key

1. Select **Add AI Provider Key**.
2. In the dialog, enter **Name**, choose **Provider** as **OpenAI**, and paste the **API Key**.
3. Select **Add Key**. Select **Cancel** to close the dialog without saving.
   Doc Holiday sends a real OpenAI verification call before it saves the key, and it rejects keys that cannot run inference.

## Manage active and failover keys

Each key card shows **Active** and the overflow menu actions **Test**, **Set Active**, and **Delete**.

1. The first OpenAI key becomes active automatically.
2. Open a key card and select **Set Active** to move the active badge to that key. Doc Holiday demotes the previous active key to failover.
3. If Doc Holiday rejects the active key, it uses a failover key on the next piece of work.
4. Doc Holiday checks key state fresh for each request, so changes apply to the next piece of work, including work already in flight.

## Test and delete a key

1. Open the overflow menu on any key card and select **Test** whenever needed.
2. Review the result. Doc Holiday shows **Key is valid** when the key works and **Key test failed** when it does not.
3. Open the overflow menu again and select **Delete** to remove a key.
4. Confirm **Delete AI provider key?**. The dialog also offers **Cancel**. Doc Holiday deletes the stored key and scrubs the secret.

## Next

- Start setup in [Add your OpenAI key](/b6-add-your-openai-key.md).
- Review [Billing and plans](/h4-billing-and-plans.md) for plan coverage and Enterprise inference.

If every key fails, the work errors.