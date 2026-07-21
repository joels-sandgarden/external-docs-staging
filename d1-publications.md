# Publications

A Publication is the unit Doc Holiday keeps current. You use it to define one documentation destination, the Sources that supply context, and the guidance that shapes the work it produces. When you open a Publication, you are looking at the scope for a request, the draft, and the result.

## What a Publication points at

A Publication points at the Sources it reads for context and change signals, and it points at exactly one documentation destination that it writes into. That destination can live in a repository separate from the code, which keeps the documentation site and the source of truth in the same Publication without merging them into one place. A Publication can also point at a Slack channel when a team wants notifications in chat.

This setup matters because a Publication is not a single page or file. It gives you one documentation workspace: the destination where pages live, and the Sources that explain what changed and why.

## What a Publication controls

A Publication controls which kinds of output Doc Holiday may produce. You can enable documentation, release notes, changelogs, or any combination of those output types. See [output types](/d3-output-types.md) for the kinds of content each option represents.

It also controls when Doc Holiday reacts on its own. Triggers tell the product which events should open or resume work for that Publication, so changes in connected Sources can turn into new documentation work without a manual request. See [configure triggers](/d2-configure-triggers.md) for the events that can start that work.

The Publication also carries the writing guidance that keeps its output consistent. Style guides, planning instructions, and instructions from the Library shape the voice and structure of the work under that Publication. The Library provides shared instructions that can apply across Publications or only to selected ones. See [the Library](/e1-the-library.md) for that shared guidance model.

## Why the boundary matters

A Publication lets Doc Holiday keep several kinds of output in one place without blurring the source of truth. The same Publication can lead to a documentation page, a release note, and a changelog entry when those pieces describe the same product area. Because those outputs share the same Sources and the same guidance, the result stays aligned even when the work begins from different triggers.

The boundary also makes the setup easier to understand at a glance. You can see which Sources drive the content, which destination receives it, and which instructions shape the writing. That shared contract gives everyone the same frame for judging whether the Publication matches the work it is meant to cover.

That matters when the documentation repo lives apart from the code. The Publication keeps that split visible, so the destination never looks like an afterthought and the Sources never look like a loose list of inputs.

## How people read a Publication

When you review a Publication, you can see the Sources that drive it, the destination that receives output, and the kinds of content it may create. Product managers, writers, support engineers, and software engineers use that view to understand why one request turns into a new guide while another turns into a release note or changelog entry.

The Publications area also makes access visible. When the right people can see the same configuration, they can judge whether the Publication still matches the work it covers before they start a new request. That helps the Publication act as a clear contract instead of a loose collection of settings.

You can enable documentation, release notes, or changelogs without creating a separate workspace for each one, as long as the same Publication should govern them.

That keeps the setup compact even when the Publication covers more than one document type.

## What work looks like under a Publication

Every request becomes a Work History entry for one Publication. You can trace the context, the drafts Doc Holiday proposes, and the outcome in one place. The Publication keeps each request tied to the right documentation set.

Work History also helps you see continuity. When the same Publication keeps receiving updates, the record shows how Doc Holiday moved from one request to the next and how the docs changed over time. See [Work History](/f4-work-history.md) for the record of that work.

## Publication health

Publication health gives you a quick read on whether Doc Holiday can reach the configured Sources and documentation destination. A healthy Publication shows that the connected inputs and destination are ready for work. When something goes wrong, the health badge helps you spot it quickly.

Health does not promise that every request will succeed. It only tells you whether Doc Holiday can reach the configured Sources and destination right now. That makes it a fast check for access issues, missing setup, or a destination that no longer matches the Publication.

The run test action adds a quick confirmation that the current setup still fits together. It helps surface a problem early, before a new request depends on it.

In the Publications area, the details and status panels show the inputs, the target destination, the optional notifier, the enabled outputs, the last updated time, user access, and the health badge with its run test action. That view gives you a concise picture of what the Publication controls and whether it is ready.

## Next

- [Create your first Publication](/b5-create-your-first-publication.md)
- [Manage Publications](/d5-manage-publications.md)