# Publications

A Publication is the unit Doc Holiday keeps current. It defines the documentation destination, the Sources that supply context, and the guidance that shapes the work it produces. Most work in Doc Holiday starts by choosing the Publication it belongs to, because the Publication sets the scope for the request, the draft, and the result.

## What a Publication points at

A Publication points at the Sources it reads for context and change signals, and it points at exactly one documentation destination that it writes into. That destination can live in a repository that is separate from the code, and Doc Holiday supports that arrangement as a normal setup. A Publication can also point at a Slack channel for notifications when a team wants updates in chat.

This structure matters because Doc Holiday does not treat a Publication as a single page or file. It treats it as the boundary for a connected documentation workspace, linking the place where documentation lives with the Sources that explain what changed and why.

## What a Publication controls

A Publication controls which kinds of output Doc Holiday may produce. It can enable documentation, release notes, changelogs, or any combination of those output types. See [output types](/d3-output-types.md) for the kinds of content each option represents.

It also controls when Doc Holiday reacts on its own. Triggers tell the product which events should open or resume work for that Publication, so changes in connected Sources can turn into new documentation work without a manual request. See [configure triggers](/d2-configure-triggers.md) for the events that can start that work.

The Publication also carries the writing guidance that keeps its output consistent. Style guides, planning instructions, and instructions from the Library shape the voice and structure of the work that appears under that Publication. The Library provides shared instructions that can apply across Publications or only to selected ones. See [the Library](/e1-the-library.md) for that shared guidance model.

## Why the boundary matters

A Publication lets Doc Holiday keep several kinds of output in one place without blurring the source of truth. The same Publication can lead to a documentation page, a release note, and a changelog entry when those pieces describe the same product area. Because those outputs share the same Sources and the same guidance, the result stays aligned even when the work begins from different triggers.

The boundary also makes the setup easier to understand at a glance. A team can see which Sources drive the content, which destination receives it, and which instructions shape the writing. That shared contract gives everyone the same frame for judging whether the Publication matches the work it is meant to cover.

## How people read a Publication

A Publication gives product managers, writers, support engineers, and software engineers the same frame for the same documentation set. A person reviewing the Publication can see the Sources that drive it, the destination that receives output, and the kinds of content it may create. That shared view makes it easier to understand why one request turns into a new guide while another turns into a release note or a changelog entry.

The Publications area also makes access visible. When the right people can see the same configuration, they can judge whether the Publication still matches the work it covers before they start a new request. That helps the Publication act as a clear contract instead of a loose collection of settings.

## What work looks like under a Publication

Every request becomes a Work History entry for one Publication. That entry gathers the context for the work, the drafts that Doc Holiday proposes, and the outcome that follows. The Publication gives each request a clear home and keeps the record of the work attached to the right documentation set.

Work History also helps readers understand continuity. When the same Publication keeps receiving updates, the record shows how Doc Holiday moved from one request to the next and how the docs changed over time. See [Work History](/f4-work-history.md) for the record of that work.

## Publication health

Publication health gives a quick read on whether Doc Holiday can work with the Publication’s configured Sources and documentation destination. A healthy Publication signals that the connected inputs and destination are ready for work. When something is wrong, the health badge helps readers spot it quickly.

Health does not promise that every request will succeed. It only tells whether Doc Holiday can reach the configured Sources and destination now. That makes it a fast check for access issues, missing setup, or a destination that no longer matches the Publication.

The run test action adds a quick confirmation that the current setup still fits together. It helps surface a problem early, before a new request depends on it.

In the Publications area, the details and status panels show the inputs, the target destination, the optional notifier, the enabled outputs, the last updated time, user access, and the health badge with its run test action. That view gives a concise picture of what the Publication controls and whether it is ready.

## Next

- [Create your first Publication](/b5-create-your-first-publication.md)
- [Manage Publications](/d5-manage-publications.md)