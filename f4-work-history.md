# Work History

Work History records one documentation request from its first trigger to its final result. Each entry belongs to one [Publication](/a3-concepts.md) and one [Source](/a3-concepts.md), so the reader can follow one stream of work without mixing it with another. A request can begin in a Source comment, a trigger event, the app, or the API.

The page shows the request as it moves through its lifecycle. Doc Holiday starts in Running while it works. When the draft is ready, the entry moves to Ready for Review. From there, the work can move to Open, Merged, Closed, Cancelled, or Needs Attention. Open means the draft has opened for review. Merged means the changes landed. Closed means the review ended without landing the changes. Cancelled means someone stopped running work before it finished. Needs Attention means Doc Holiday wants a reply in Messages, so the reader should open that tab and answer there.

A single Work History entry can take more than one pass. A new comment or reply can start another pass, and each pass can propose changes to one or more files. The Files tab shows those proposed changes, so the reader can review them before the work moves ahead. The Messages tab keeps the thread attached to the entry and makes follow-up replies easy to find.

The Work History page in the app lists these entries for one Publication at a time. The Publication filter narrows the list, and the status filter narrows it by lifecycle stage. The list can still show Cancelled when the work stops, even though the filter menu does not promise to expose every status label shown in the list.

Each row in the list shows the Publication name, a summary, the current status, and the start and last update times. That gives the reader a quick view of what is active and what has already finished.

For the full status reference, see [Work History states](/j10-work-history-states.md).

| App label | What it means | What moves it forward |
| --- | --- | --- |
| Running | Doc Holiday is working on the request. | A new pass can keep the work moving, or someone can stop it. |
| Ready for Review | The draft is ready for inspection. | Open [Review and revise](/f3-review-and-revise.md) to review the draft. |
| Open | The draft is open for review. | Review comments can trigger another pass, or the request can move on to a final result. |
| Merged | The changes landed in the Publication. | The entry is complete. |
| Closed | The review ended without landing the changes. | A new request can reopen the topic. |
| Cancelled | Someone stopped the running work. | A new request can start the work again. |
| Needs Attention | Doc Holiday needs a reply in Messages. | Open Messages and reply there. |