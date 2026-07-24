# Publications

## Overview

A Publication is the defined set of documentation Doc Holiday writes and maintains. It gives shape to the work that stays current over time, so most requests begin by choosing the Publication they belong to. In the UI, the Publication form shows Sources as **Inputs** and the documentation destination as **Targets**. A Publication is larger than a single page: it represents the connected body of documentation Doc Holiday keeps in sync as the product changes. It also carries the writing guidance that keeps the output consistent and can include optional Slack notifications.

## What a Publication points at

A Publication points at any number of Sources, shown as **Inputs** in the publication form, for context and change signals, exactly one docs destination, shown as **Targets**, for the writing output, and an optional Slack channel for notifications. The Sources can cover different parts of a product or even different systems, while the docs destination stays singular so the published documentation has one clear home. The Slack channel adds visibility for teams that want progress updates without sending the documentation to a second destination. That keeps notifications useful without turning them into another place where the content must live.
That helps teams spot progress where they already coordinate work. See [Slack notifications](/g4-slack-notifications.md) for details.

That structure lets one Publication gather information from several places without fragmenting the writing target. Doc Holiday can read code changes from one Source, product context from another, and supporting material from a third, then keep the resulting documentation together in one destination. The docs destination can also live in a repository separate from the code repository, which is a normal and fully supported setup. That separation helps teams keep the documentation site, the codebase, and the surrounding context in the places that fit their workflow. It also makes it easier to grow a Publication over time, because new Sources can join the same documentation destination without changing where readers find the result.

## What a Publication controls

A Publication controls three things: output types, trigger behavior, and writing guidance. Output types decide whether Doc Holiday produces Documentation, Release Notes, Changelog, or a combination of them; see [Output types](/d3-output-types.md) for the full set of options. Those choices let a Publication focus on the kinds of writing that matter for its audience instead of trying to cover everything at once. They also let one Publication produce only the content its readers need, instead of forcing every format into every request. The controls work together so a Publication can define what Doc Holiday should watch, what it should produce, and which writing guidance it should follow when it responds.

Trigger behavior decides when Doc Holiday reacts to a Source, and [trigger configuration](/d2-configure-triggers.md) explains how those events are selected. Writing guidance comes from [the Library](/e1-the-library.md), which holds reusable instructions that can apply to one Publication or many. Those instructions can include style guides, planning instructions, and other shared direction that keep the voice and structure consistent across related Publications. The Library gives teams a single place to express shared expectations, while each Publication still keeps the guidance that fits its own output. Together, the three controls let a Publication define what counts as a relevant event, what output belongs to that event, and how the resulting writing should sound.

## Work History and lifecycle

Every request becomes a Work History entry scoped to one Publication. That scope keeps the record tied to the same documentation destination, Sources, and writing guidance that shaped the request, which makes the history easy to read later. Each entry shows the request from the first trigger through the final result, so a reader can follow one Publication without sorting through unrelated work. An entry can move through visible states such as running, ready for review, open, needs attention, merged, closed, or cancelled.

The page for [Work History](/f4-work-history.md) explains that record in more detail and shows how it helps people trace the outcome of a request without leaving the Publication it belongs to.

## Publication health

Publication health shows whether the Publication, its Sources, and its docs destination are ready for Doc Holiday to use. In the Publications list, health appears as a badge. On the publication details page, it appears in a status section that brings the current state into view. The badge gives the quick read, while the details page adds the **Run Test** button and the troubleshooting guidance when health is unhealthy. A healthy Publication gives a clear signal that the docs destination and connected Sources are ready. In both places, the status turns a setup check into something visible and easy to act on.

## Next

Continue with [Create your first Publication](/b5-create-your-first-publication.md) or [Manage Publications](/d5-manage-publications.md).

---

<!-- doc-holiday-watermark -->
<p align="center">
  <a href="https://doc.holiday">
    <img alt="Doc Holiday logo" src="https://doc.holiday/assets/docs-by-doc-holiday.png" width="200">
  </a>
</p>
<p align="center">Docs authored by <a href="https://doc.holiday">Doc Holiday</a></p>
