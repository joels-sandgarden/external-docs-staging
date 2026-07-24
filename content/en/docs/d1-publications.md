---
title: Publications
url: "docs/publications"
description: "What a Publication defines and controls."
---

## Overview

A Publication is the defined set of documentation Doc Holiday keeps current over time. It marks the boundary for one documentation area, so related pages, writing guidance, and requests stay attached to the same place. Most work starts by choosing the Publication it belongs to.

That boundary keeps one documentation area moving together instead of treating each page as separate work. When the product changes, Doc Holiday keeps that area current as one unit, so related pages stay aligned as a group.

## What a Publication points at

A Publication points at any number of Sources under **Inputs**, exactly one docs destination under **Targets**, and an optional Slack channel for notifications. Inputs can cover different parts of a product or different systems, while Targets give the published documentation one clear home. The Slack channel adds visibility for teams that want progress updates without turning notifications into another destination for the content.

That boundary keeps one set of Inputs, one Target, and one stream of writing guidance together. Doc Holiday can read code changes from one Source, product context from another, and supporting material from a third, then keep the resulting documentation in one destination. See [Slack notifications](./g4-slack-notifications.md) for details.

## What a Publication controls

A Publication controls three things: output types, trigger behavior, and writing guidance. Output types decide whether Doc Holiday produces Documentation, Release Notes, Changelog, or a combination of them; see [Output types](./d3-output-types.md) for the full set of options. Those choices let a Publication focus on the kinds of writing that matter for its audience instead of trying to cover everything at once.

Trigger behavior decides when Doc Holiday reacts to a Source, and [trigger configuration](./d2-configure-triggers.md) explains how those events are selected. Writing guidance comes from [the Library](./e1-the-library.md), which holds reusable instructions that can apply to one Publication or many. Those instructions can include style guides, planning instructions, and other shared direction that keep the voice and structure consistent across related Publications.

## Work History and lifecycle

Every request becomes a Work History entry for one Publication. That scope keeps the record attached to the same Inputs, Targets, and writing guidance that shaped the request, which makes the history easier to read later. Work History shows the full lifecycle of the request for that Publication, from the first trigger through the final result, instead of mixing it with unrelated work elsewhere in the product.

That narrow scope matters when a team wants to understand why a page changed, what changed next, or which request still needs attention. Each entry stays easy to trace because the visible history belongs to one Publication, not to the organization at large. A single Publication can accumulate many requests over time, and Work History keeps them readable as a sequence rather than as isolated edits. The page for [Work History](./f4-work-history.md) explains that record in more detail and shows how it helps people trace the outcome of a request without leaving the Publication it belongs to.

## Publication health

Publication health shows whether the Publication, its Inputs, and its Targets are ready for Doc Holiday to use. Healthy means the Publication, its Inputs, and its Targets are ready for new work. Unhealthy means one or more of them need attention before the next request can proceed. In the Publications list, health appears as a badge. On the publication details page, it appears in a status section that brings the current state into view.

That status makes the difference between a Publication that can accept work and one that needs attention easy to spot. When health is unhealthy, the details page shows the **Run Test** button and the troubleshooting guidance so the next check stays visible and easy to understand. The result is a simple scan for the list view and a clearer readiness check for the details view.

## Next

Continue with [Create your first Publication](./b5-create-your-first-publication.md) or [Manage Publications](./d5-manage-publications.md).