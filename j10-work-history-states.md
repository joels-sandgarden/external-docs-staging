# Work History states

Work History uses backend status values, but the app shows readers a smaller set of labels. This page maps those labels to the underlying values for quick lookup.

## Conversation status values

| API value | app label | meaning | what moves it forward |
| --- | --- | --- | --- |
| `open` | `Open` | The request is active and can take more work. | A new pass starts running, or a reply adds more context. |
| `staged` | `Ready for Review` | The draft waits for review. | Releasing the staged draft moves it to `Open`. |
| `running` | `Running` | Doc Holiday is working on the request. | The current pass finishes and settles into the next result. |
| `closed` | `Closed` | The request ended without a merge. | Start a new request to continue the work. |
| `merged` | `Merged` | The proposed changes reached the docs repository. | The merge completes and the result records here. |
| `cancelled` | `Cancelled` | The request stopped before completion. | Start a new request to try again. |
| `needsAttention` | `Needs Attention` | The latest staged pass needs a reply. | A reply in Messages lets the next pass continue. |

The app shows `Needs Attention` only when a staged conversation's latest bot comment includes `⚠️` or `🙋`.

## Turn status values

| API value | app label | meaning |
| --- | --- | --- |
| `running` | `Running` | The pass is in progress. |
| `success` | `Completed` | The pass finished successfully. |
| `skipped` | `Skipped` | The pass did not run. |
| `error` | `Failed` | The pass stopped with an error. |
| `no_changes` | `No Changes` | The pass found nothing to change. |
| `cancelRequested` | Not surfaced | A cancel request is in progress. |
| `cancelled` | `Cancelled` | The pass stopped after cancellation. |

Retry is available only for `error` turns, and retry sends the turn back to `running`.

## See also

- [Work History overview](/f4-work-history.md)
- [API reference for Work History](/j4-api-work-history.md)