# Work History

Work History records one documentation request from trigger to result. Each entry stays scoped to one [Publication](/a3-concepts.md) and one [Source](/a3-concepts.md), so a single request remains easy to follow without mixing it with unrelated work. Use Work History when a request needs a quick status check without reading the full thread or going back to the source that started it. It shows what Doc Holiday is doing now, what it has already finished, and where review or a reply is still needed.

The lifecycle tells the story of the request. Running means Doc Holiday is still working. Ready for Review marks the handoff from drafting to human review. Open means the review is active and still collecting feedback. Merged means the changes landed in the Publication. Closed means the review ended without landing the changes. Cancelled means someone stopped the work. Needs Attention means Doc Holiday is asking for help, so open Messages and reply there. A request can stay active through several follow-up passes before it reaches one of those results.

A Work History entry can go through several passes. A new comment or reply can start another pass, and each pass can propose changes to one or more files. The Files tab shows those proposed changes at file level. The Messages tab keeps the thread with the entry, so follow-up replies stay attached to the same request.

That structure keeps one request readable from the first trigger to the final result. It also shows how the work changed over time, which matters when a draft is revised more than once before it settles. Because every pass stays inside the same entry, you can compare the current draft with earlier attempts instead of chasing separate records.

The list shows one Publication at a time. Use the Publication filter to narrow the list to a single destination, and use the status filter to narrow it to a lifecycle stage. Filters only change the view; they do not change the request. When several Publications share a workspace, or when only one stage matters, filtering keeps the view readable. Each row shows the Publication name, a short summary, the current status, and the start and last update timestamps. That makes it easy to scan active work, spot finished work, and reopen the right entry when a reply changes the next step.

For the full status reference, see [Work History states](/j10-work-history-states.md). When an entry is Ready for Review, use [Review and revise](/f3-review-and-revise.md) to inspect the draft before it moves forward.

| App label | What it means | What moves it forward |
| --- | --- | --- |
| Running | Doc Holiday is working on the request. | A new pass keeps the work moving, or someone stops it. |
| Ready for Review | The draft is ready for inspection. | Open [Review and revise](/f3-review-and-revise.md) to review it. |
| Open | The review is active and can still collect feedback. | Review comments can start another pass, or the request can reach a final result. |
| Merged | The changes landed in the Publication. | The entry is complete. |
| Closed | The review ended without landing the changes. | A new request can reopen the topic. |
| Cancelled | Someone stopped the running work. | A new request can start the work again. |
| Needs Attention | Doc Holiday needs a reply in Messages. | Open Messages and reply there. |