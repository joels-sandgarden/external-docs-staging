---
title: Concepts
url: "docs/concepts"
description: "The shared vocabulary: Publication, Source, the Library, and Work History."
---

Doc Holiday uses a shared vocabulary for where documentation belongs, where source information comes from, and how work moves from request to result.
Read this page first when the rest of the docs starts using those terms.

## Organization

An Organization is the top-level account for a workspace.
It gives every other concept a shared home for settings, content, and guidance.
It owns Publications, Sources, and the Library.

## Publication

A Publication is the maintained set of documentation Doc Holiday keeps current for one area of the product, one topic, or one release surface.
It names a body of content rather than a single page, so one Publication can cover several related pages, outputs, or audiences.
A Publication points at Sources instead of owning them, so it defines what the docs set covers while the Sources define where the information comes from and where the finished work belongs.

## Sources

Sources are the connected systems that feed Doc Holiday and receive its output.
One Source can provide context for a Publication, another can accept documentation updates, and another can do both.
A Publication points to Sources rather than owning them, so [Sources](./c1-sources.md) tell Doc Holiday what it can verify, what it can write, and how the finished work should appear.

## The Library and instructions

The Library is the organization-wide collection of editable guidance, and [the Library](./e1-the-library.md) keeps that shared direction visible for every Publication in the Organization.
Each instruction is one entry in the Library, and it can apply to every Publication or only to selected Publications.
The Library gives each Publication the same source of guidance while still letting it use the instructions it needs for its own subject matter and audience.

## Work History

Work History is the record of one documentation request from the first signal to the final result.
Each entry belongs to one Publication and one Source.
A single entry opens when something triggers it, moves through review and revision, and settles into a result such as Ready for Review, Merged, Closed, Cancelled, or Needs Attention; [Work History](./f4-work-history.md) keeps that path visible when the request needs another round of comments or another look.

Something happens in a Source. Doc Holiday turns that change into reviewed documentation in a Publication. The Library guides the writing. Work History records the result in one loop from the first request to the final page.
This model keeps the vocabulary connected from input to outcome, so the rest of the documentation stays consistent even when a request needs several passes before it settles.