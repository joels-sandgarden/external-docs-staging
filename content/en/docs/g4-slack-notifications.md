---
title: Slack Notifications
url: "docs/slack-notifications"
description: "Send Doc Holiday notifications to Slack."
---

This guide sets up Slack notifications for a Publication. Use it when you want Doc Holiday to send a Slack message after work merges.

1. Open the Sources page, then the **Providers** tab.
2. Select **Add Provider**, choose **Slack Application**, then click **Connect Slack Workspace**. Finish the Slack install flow.
3. Create a Slack Channel source under that provider. Fill in **Source Name**, **Slack Workspace**, and **Channel**. Use **Select a workspace...** to pick the workspace. If no channel is selected yet, the control shows **Select a channel...**. When channels are still loading, it shows **Loading channels...**. Use **Search channels...** to find one, and **No channels found...** appears when the list is empty.

```text
SCREENSHOT PLACEHOLDER: slack-notifications/channel-form.png
```

When you save the source, Doc Holiday joins the channel.

4. Open the Publication form and set **Notify** to the Slack Channel source. The Publication form shows **optional** next to **Notify**. Use **Select notifier** to choose the source, or leave **None** selected to keep notifications off for that Publication.

## What you get

When work merges, Doc Holiday sends a Slack message with a summary and a link to the merged work.

## Verify

Merge a small change, such as a one-line typo fix, and confirm that the Slack message arrives in the channel.

## Next

- [Manage publications](./d5-manage-publications.md)
- [Manage connections](./c7-manage-connections.md)