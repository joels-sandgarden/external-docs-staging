# Work History

Work History records one documentation request from the first trigger to the final result. It keeps that record for a single [Publication](/a3-concepts.md) and [Source](/a3-concepts.md), so the reader can follow one stream of work without mixing it with another Publication. A request can begin in a Source comment, a trigger event, the app, or the API.

The page shows the request as it moves through its lifecycle. Doc Holiday starts in Running while it works. When the draft is ready, the entry moves to Ready for Review. From there, the work can move to Open, Merged, Closed, Cancelled, or Needs Attention. Open means the draft has opened for review. Merged means the changes landed. Closed means the review ended without landing the changes. Cancelled means someone stopped running work before it finished. Needs Attention means Doc Holiday wants a reply in Messages, so the reader should open that tab and answer there.

A single Work History entry can take more than one pass. A new comment or reply can start another pass, and each pass can propose changes to one or more files. The Files tab shows those proposed changes, so the reader can review them before the work moves ahead. The Messages tab keeps the thread attached to the entry and makes follow-up replies easy to find.

The Work History page in the app lists these entries for the selected Publication. The Publication filter narrows the list to one Publication at a time, and the status filter narrows it by lifecycle stage. The list can still show Cancelled when the work stops, even though the filter menu does not promise to expose every status label shown in the list.

Each row in the list shows the Publication name, a summary, the current status, and the start and last update times. That gives the reader a quick view of which requests are still active and which ones already reached a final result.

For the full status reference, see [Work History states](/j10-work-history-states.md).

| App label | What it means | What moves it forward |
| --- | --- | --- |
| Running | Doc Holiday is working on the request. | Another pass can keep the work moving, or the request can stop. |
| Ready for Review | The draft is ready for inspection. | Open [Review and revise](/f3-review-and-revise.md) to review the draft. |
| Open | The draft is open for review. | Review comments can lead to another pass, or the work can close out. |
| Merged | The changes landed in the Publication. | The entry is complete. |
| Closed | The review ended without landing the changes. | A new request can reopen the topic. |
| Cancelled | Someone stopped the running work. | A new request can start the work again. |
| Needs Attention | Doc Holiday needs a reply in Messages. | Open Messages and respond there. |