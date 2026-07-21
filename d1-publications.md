# Publications

## Overview

A Publication is the defined set of documentation Doc Holiday writes and maintains. It gives shape to the work that stays current over time, so most requests begin by choosing the Publication they belong to. That choice matters because it ties together the Sources it reads, the destination it writes to, and the writing guidance that keeps the output consistent. A Publication is larger than a single page: it represents the connected body of documentation Doc Holiday is responsible for keeping in sync as the product changes. It also acts as the boundary for day to day documentation work, so changes, review, and follow up stay anchored to one place. That framing helps Doc Holiday keep one place current while the surrounding product continues to change.

## What a Publication points at

A Publication points at one or more Sources for context and change signals, exactly one docs destination for the writing output, and an optional Slack channel for notifications. The Sources can cover different parts of a product or even different systems, while the docs destination stays singular so the published documentation has one clear home. The Slack channel adds visibility for teams that want progress updates without sending the documentation to a second destination. That keeps notifications useful without turning them into another place where the content must live.

That structure lets one Publication gather information from several places without fragmenting the writing target. Doc Holiday can read code changes from one Source, product context from another, and supporting material from a third, then keep the resulting documentation together in one destination. The docs destination can also live in a repository separate from the code repository, which is a normal and fully supported setup. That separation helps teams keep the documentation site, the codebase, and the surrounding context in the places that fit their workflow. It also makes it easier to grow a Publication over time, because new Sources can join the same documentation destination without changing where readers find the result.

## What a Publication controls

A Publication controls three things: output types, trigger behavior, and writing guidance. Output types decide whether Doc Holiday produces documentation, release notes, changelogs, or a combination of them; see [Output types](/d3-output-types.md) for the full set of options. Those choices let a Publication focus on the kinds of writing that matter for its audience instead of trying to cover everything at once. They also let one Publication produce only the content its readers need, instead of forcing every format into every request. The controls work together so a Publication can define what Doc Holiday should watch, what it should produce, and which writing guidance it should follow when it responds.

Trigger behavior decides when Doc Holiday reacts to a Source, and [trigger configuration](/d2-configure-triggers.md) explains how those events are selected. Writing guidance comes from [the Library](/e1-the-library.md), which holds reusable instructions that can apply to one Publication or many. Those instructions can include style guides, planning instructions, and other shared direction that keep the voice and structure consistent across related Publications. The Library gives teams a single place to express shared expectations, while each Publication still keeps the guidance that fits its own output. Together, the three controls let a Publication define what counts as a relevant event, what output belongs to that event, and how the resulting writing should sound.

## Work History and lifecycle

Every request becomes a Work History entry scoped to one Publication. That scope keeps the record attached to the same documentation destination, Sources, and writing guidance that shaped the request, which makes the history easier to read later. Work History shows the full lifecycle of the request for that Publication, from the first trigger through the final result, instead of mixing it with unrelated work elsewhere in the product.

That narrow scope matters when a team wants to understand why a page changed, what changed next, or which request still needs attention. Each entry stays easy to trace because the visible history belongs to one Publication, not to the organization at large. A single Publication can accumulate many requests over time, and Work History keeps them readable as a sequence rather than as isolated edits. That structure also makes it easier to compare past requests, since the history uses the same Publication as its frame of reference every time. An entry can move through visible states such as ready for review, completed, cancelled, or needing attention. The page for [Work History](/f4-work-history.md) explains that record in more detail and shows how it helps people trace the outcome of a request without leaving the Publication it belongs to.

## Publication health

Publication health shows whether the Publication, its Sources, and its docs destination are ready for Doc Holiday to use. It gives a quick readiness signal before work starts and a more detailed view when someone opens the Publication itself. In the Publications list, health appears as a badge. On the publication details page, it appears in a status section that brings the current state into view.

That status makes the difference between a Publication that can accept work and one that needs attention easy to spot. A healthy Publication gives a clear signal that the docs destination and connected Sources are ready. When health is unhealthy, the details page shows a retry action and troubleshooting guidance so the next check stays visible and easy to understand. The result is a simple scan for the list view and a deeper explanation for the details view. In both places, the status turns a setup check into something visible and easy to act on.

## Next

Continue with [Create your first Publication](/b5-create-your-first-publication.md) or [Manage Publications](/d5-manage-publications.md).