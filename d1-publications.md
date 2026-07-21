# Publications

## Overview

A Publication is the defined set of documentation Doc Holiday writes and maintains. It gives shape to the work that stays current over time, so most requests begin by choosing the Publication they belong to. That choice matters because it ties together the sources of context, the destination for the documentation, and the writing guidance that keeps the output consistent.

## What a Publication points at

A Publication points at one or more Sources for context and change signals, exactly one docs destination for the writing output, and an optional Slack channel for notifications. The Sources can cover different parts of a product or even different systems, while the docs destination stays singular so the published documentation has one clear home.

That structure lets one Publication gather information from several places without fragmenting the writing target. Doc Holiday can read code changes from one Source, product context from another, and supporting material from a third, then keep the resulting documentation together in one destination. The docs destination can also live in a repository separate from the code repository, which is a normal and fully supported setup.

## What a Publication controls

A Publication controls three things: output types, trigger behavior, and writing guidance. Output types decide whether Doc Holiday produces documentation, release notes, changelogs, or a combination of them; see [Output types](/d3-output-types.md) for the full set of options.

Trigger behavior decides when a Source should start a new request, and [trigger configuration](/d2-configure-triggers.md) explains how those events are selected. Writing guidance comes from [the Library](/e1-the-library.md), which holds reusable instructions that can apply to one Publication or many. Those instructions can include style guides, planning instructions, and other shared direction that keep the voice and structure consistent across related Publications.

## Work History and lifecycle

Every request becomes a Work History entry scoped to one Publication. That scope keeps the record attached to the same documentation destination, Sources, and writing guidance that shaped the request, which makes the history easier to read later. Work History shows the full lifecycle of the request for that Publication, from the first trigger through the final result, instead of mixing it with unrelated work elsewhere in the product.

An entry can move through visible states such as ready for review, completed, cancelled, or needing attention. The page for [Work History](/f4-work-history.md) explains that record in more detail and shows how it helps people trace the outcome of a request without leaving the Publication it belongs to.

## Publication health

Publication health shows whether the Publication, its Sources, and its docs destination are ready for Doc Holiday to use. It gives a quick readiness signal before work starts and a more detailed view when someone opens the Publication itself. In the Publications list, health appears as a badge. On the publication details page, it appears in a status section that brings the current state into view.

When health is unhealthy, the details page shows a retry action and troubleshooting guidance so the next check stays visible and easy to understand.

## Next

Continue with [Create your first Publication](/b5-create-your-first-publication.md) or [Manage Publications](/d5-manage-publications.md).