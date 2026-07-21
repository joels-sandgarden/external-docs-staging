# Publications

A Publication is the unit Doc Holiday keeps current. It defines one connected documentation destination, the Sources it listens to, and the guidance that shapes the work it produces. Most work in Doc Holiday starts by choosing the Publication it belongs to, because the Publication sets the scope for the request, the draft, and the result.

## What a Publication points at

A Publication points at the Sources it reads from for context and change signals, and it points at exactly one documentation destination that it writes into. That destination often lives in a repository that is separate from the code, and Doc Holiday supports that arrangement as a normal setup. A Publication can also point at a Slack channel for notifications when a team wants updates in chat.

This structure matters because Doc Holiday does not treat a Publication as a single page or file. It treats it as the boundary for a connected documentation workspace: one place where documentation lives, plus the Sources that explain what changed and why.

## What a Publication controls

A Publication controls which kinds of output Doc Holiday may produce. It can enable documentation, release notes, changelogs, or any combination of those output types. See [output types](/d3-output-types.md) for the kinds of content each option represents.

It also controls when Doc Holiday reacts on its own. Triggers tell the product which events should open or resume work for that Publication, so changes in the connected Sources can turn into new documentation work without a manual request. See [configure triggers](/d2-configure-triggers.md) for the events that can start that work.

The Publication also carries the writing guidance that keeps its output consistent. Style guides, planning instructions, and Library-backed instructions all shape the voice and structure of the work that appears under that Publication. The Library provides shared instructions that can apply across Publications or only to selected ones. See [the Library](/e1-the-library.md) for that shared guidance model.

## What work looks like under a Publication

Every request becomes a Work History entry that belongs to one Publication. That entry gathers the context for the work, the drafts that Doc Holiday proposes, and the outcome that follows. This is why a Publication matters so much: it gives each request a clear home and keeps the record of the work attached to the right documentation set.

Work History also helps readers understand continuity. When the same Publication keeps receiving updates, the record shows how Doc Holiday moved from one request to the next and how the docs changed over time. See [Work History](/f4-work-history.md) for the record of that work.

## Publication health

Publication health gives a quick read on whether Doc Holiday can work with the Publication’s configured Sources and documentation destination. A healthy Publication signals that the connected inputs and destination look ready for work. A problem in either place shows up quickly, so the health badge helps readers understand whether the Publication can accept new requests.

In the Publications area, the details and status panels show the inputs, the target destination, the optional notifier, the enabled outputs, the last updated time, user access, and the health badge with its run test action. That view gives a concise picture of what the Publication controls and whether it is ready.

## Next

- [Create your first Publication](/b5-create-your-first-publication.md)
- [Manage Publications](/d5-manage-publications.md)