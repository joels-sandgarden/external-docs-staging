# Publications

## Overview

A Publication is the defined set of documentation Doc Holiday keeps current. It is the unit most work starts from, because it tells Doc Holiday which docs it maintains, which Sources it reads, and which writing guidance it applies.

## What a Publication points at

A Publication points at three things:

- One or more **Sources** that provide context and change signals.
- Exactly one docs destination where Doc Holiday writes the documentation.
- An optional Slack channel for notifications.

The docs destination can live in a repository that is separate from the code repository. That setup is normal and fully supported, so the code and the docs can stay in the places that make sense for each team.

## What a Publication controls

A Publication controls the output and guidance that shape the work it receives:

- Which output types it writes, through [Output types](/d3-output-types.md).
- When it reacts on its own, through [trigger configuration](/d2-configure-triggers.md).
- Which writing guidance applies, through [the Library](/e1-the-library.md).

That guidance can include style guides, planning instructions, and other publication-specific instructions. The Library can supply reusable instructions that apply to one Publication or many, and the publication form brings those choices together with the Publication name, its Sources, its docs destination, and the optional notification channel.

## Work History and lifecycle

Every request becomes a Work History entry scoped to one Publication. Work History records the request from first trigger to final result, so the record stays attached to the Publication it affects rather than floating across the product.

A Work History entry opens, gathers the work for that Publication, and then settles into a visible result such as ready for review, completed, cancelled, or needing attention. The page for [Work History](/f4-work-history.md) explains that record in more detail.

## Publication health

Publication health shows whether the Publication and the Sources and destination it depends on are ready for Doc Holiday to use. In the Publications list, health appears as a badge. On the publication details page, it appears in a status section.

When health is unhealthy, the details page shows a retry action and troubleshooting guidance so the problem is easy to follow up.

## Next

Continue with [Create your first Publication](/b5-create-your-first-publication.md) or [Manage Publications](/d5-manage-publications.md).