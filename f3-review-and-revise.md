# Review and revise

When a Work History entry reaches Ready for Review, open its sheet and review each file. From there, you can confirm the request details, leave comments, and open the final pull request or merge request.

## Opening the entry

1. In Work History, select the entry marked Ready for Review.
2. The sheet opens with **Details**, **Files**, and **Messages**.
3. In **Details**, confirm these labels:
   - `Summary:` the request title
   - `Created By:` who started the entry
   - `Started:` when the work began
   - `Last Updated:` the latest activity
   - `Trigger:` what started the work
   - `Status:` Ready for Review
   - `Pull Request:` the docs repo link, when one exists
   - `Merged by:` who merged it, when the entry has already been merged

## Reviewing proposed file changes

The **Files** tab shows each file row, its diff count, and its status. Open a file to review the diff, then use **Discard** to remove it from the final request or **Restore** to add it back.

```text
SCREENSHOT PLACEHOLDER: review-and-revise/files-tab-diff.png
```

Inside the diff, review the lines in order. Use `Comment on specific lines` to anchor a note to one row, or `Comment on this line, or drag to select multiple` to cover more than one line. Set the range with `Start line` and `End line` when needed, then use `Add Comment` to leave feedback, `Send to Doc` to send the comment for another revision pass, or `Add to Batch` to collect several comments first. Use `Add a file-level comment` when the note applies to the whole file. Expand hidden context with `Expand unchanged lines`, and close open sections with `Collapse all expanded sections`.

## Commenting and revising

Leave inline comments on the file content when only a few lines need attention. Leave a file-level comment when the whole file needs a broader change. In **Messages**, reply with `Send a message` and then `Send` so the next update includes that context. Every comment or reply sends Doc Holiday back for another revision pass.

If you selected several comments, finish with `Send Batch to Doc`.

## Excluding files

Use **Discard** to remove a file from the final request, and **Restore** to bring it back. The approval dialog updates to show how many files stay in the request and how many are permanently discarded.

## Approving and opening the PR/MR

When the draft looks right, use **Open Pull Request** on GitHub or **Open Merge Request** on GitLab. The confirmation dialog shows how many files will be committed and how many will be permanently discarded.

```text
SCREENSHOT PLACEHOLDER: quickstart/open-pr-dialog.png
```

After approval, the opened request is a normal pull request or merge request in the docs repo, and the standard merge flow applies.

## Next steps

Continue with [Work History](/f4-work-history.md) or review [Slack notifications](/g4-slack-notifications.md).