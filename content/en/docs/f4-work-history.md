---
title: Work History
url: "docs/work-history"
description: "The record of every request and its lifecycle."
---

Work History is the running record of one documentation request from the first trigger to the final result. A request can start from a git comment, a trigger event, the app, or the API and still land in the same list. The page is the place to follow a request for a specific Publication, check whether it still needs input, or review what Doc Holiday produced. It keeps the request visible as it opens, moves through work, and settles into a result. The list shows the current stage beside each entry, so a Publication’s activity stays easy to scan. See [shared vocabulary](./a3-concepts.md).

Work History does not turn the request into a step list. The visible label always follows the request’s current condition. Running means Doc Holiday is still working on the request. Ready for Review means the draft is ready for a person to check. Open means the request is active and still collecting work. Needs Attention means Doc Holiday asked for input and is waiting for a reply. Merged means the proposed changes reached the docs repository. Closed means the request ended without a merge. Cancelled means the request stopped before completion.

One Work History entry can include more than one pass. A new comment or reply can send Doc Holiday back to the same request with fresh context, and each new message can trigger another pass. Each pass can propose changes to one file or several files. That is why the detail view includes Details, Files, Messages, Feedback, and Reasoning. Details brings together the trigger, timestamps, status, and result, so the entry reads as one continuous record instead of several disconnected events. Files shows the proposed file changes and file actions. Messages is where the requester replies when Doc Holiday asks for input, Feedback captures the reviewer’s response, and Reasoning explains why the draft took its current shape. Each pass stays attached to the same Work History entry.

The Work History page helps readers find the right entry quickly when the list grows. It includes a Publication filter, a status filter, and a summary search box that filters entries by their summary text, and the list narrows as any of them changes. When several Publications are active, the Publication filter narrows the working set without changing what any entry means. The status filter does the same when many requests are in flight, so a reviewer can focus on active work or on entries that need a reply. Because the filters only narrow what appears on screen, the entry’s meaning stays the same no matter how the list is sliced. The All statuses view shows every entry. That makes it easy to focus on one Publication, compare only active requests, or jump straight to entries that need a reply. Filtering by Publication keeps attention on the right destination, and filtering by status trims the list to the entries that need action now. When the list is crowded, the filters turn a long queue into a short working set.

For a fuller status reference, see [/j10-work-history-states.md](./j10-work-history-states.md). When an entry reaches Ready for Review, [/f3-review-and-revise.md](./f3-review-and-revise.md) explains the next step.

| App label | What it means | What moves it forward |
| --- | --- | --- |
| Running | Doc Holiday is still working on the request. | More work completes, or the request moves to review. |
| Ready for Review | The draft is ready for a person to check. | A review, reply, or approval moves the request on. |
| Open | The request is active and still collecting work. | New comments, replies, or updates keep the work moving. |
| Needs Attention | Doc Holiday asked for input and is waiting on a reply. | A response in Messages lets the next pass continue. |
| Merged | The changes reached the Publication’s docs repository. | The merge completes and the result is recorded. |
| Closed | The request ended without a merge. | No further work moves it on. |
| Cancelled | The request stopped before completion. | A new request starts a fresh Work History entry. |
