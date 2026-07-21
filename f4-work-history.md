# Work History

Work History records one documentation request from its first trigger to its final result. Each entry belongs to one [Publication](/a3-concepts.md) and one [Source](/a3-concepts.md), which keeps a single request visible without mixing it with unrelated work. Use Work History when you want to see what Doc Holiday did, what it still needs to finish, and whether a request moved far enough for review or publication. A request can begin in a Source comment, a trigger event, or a request in the app, but it always lands in the same record so the history stays easy to follow.

The lifecycle tells the story of the request. Doc Holiday starts in Running while it works on the request. When the draft is ready, the entry moves to Ready for Review. From there, the request can move to Open, Merged, Closed, Cancelled, or Needs Attention. Open means the draft is open for review and can still collect feedback. Merged means the changes landed in the Publication. Closed means review ended without landing the changes. Cancelled means someone stopped the work before it finished. Needs Attention means the latest bot reply asks for help, so open Messages and reply there instead of waiting on the list.

A single Work History entry can go through multiple passes. A new comment or reply can trigger another pass, and each pass can propose changes to one or more files. That makes the entry more like a running record than a one-time snapshot: the request can change shape as people review the draft, ask for edits, or respond to questions. The Files tab shows the proposed file changes for each pass, which lets the reader inspect the draft at the file level before the work advances. The Messages tab keeps the thread attached to the entry so follow-up replies stay in the same place.

That lifecycle matters because Work History shows both progress and outcome. A request can sit in Running while the draft takes shape, move to Ready for Review when a person can inspect it, and then settle into a final state that explains whether the documentation landed. The list keeps those stages visible without forcing the reader to open each entry first.

The Work History page in the app lists these entries for one Publication at a time. The Publication filter narrows the list to one destination, and the status filter narrows it to one lifecycle stage. Each row shows the Publication name, a summary, the current status, and the start and last update timestamps. That gives the reader a fast way to scan active work, see what already finished, and jump back into the right entry when a reply or review needs attention.

For the full status reference, see [Work History states](/j10-work-history-states.md). When an entry is Ready for Review, use [Review and revise](/f3-review-and-revise.md) to inspect the draft before it moves forward.

| App label | What it means | What moves it forward |
| --- | --- | --- |
| Running | Doc Holiday is working on the request. | A new pass can keep the work moving, or someone can stop it. |
| Ready for Review | The draft is ready for inspection. | Open [Review and revise](/f3-review-and-revise.md) to review the draft. |
| Open | The draft is open for review. | Review comments can trigger another pass, or the request can move on to a final result. |
| Merged | The changes landed in the Publication. | The entry is complete. |
| Closed | The review ended without landing the changes. | A new request can reopen the topic. |
| Cancelled | Someone stopped the running work. | A new request can start the work again. |
| Needs Attention | Doc Holiday needs a reply in Messages. | Open Messages and reply there. |