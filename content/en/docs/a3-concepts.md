---
title: Concepts
url: "docs/concepts"
description: "The shared vocabulary: Publication, Source, the Library, and Work History."
---

Doc Holiday uses a shared vocabulary for where documentation belongs, where source information comes from, and how work moves from request to result.
Read this page first when the rest of the documentation uses those terms.

## Organization

An Organization is the top-level account for a workspace.
It owns Publications, Sources, and the Library.

## Publication

A Publication is the set of documentation Doc Holiday keeps current for one area of the product.
It names a body of content rather than a single page, and it points at Sources instead of owning them.

## Sources

Sources are the connected systems that provide context or receive documentation.
A Publication points at one Source that receives the documentation and at other Sources for context.
[Sources](./c1-sources.md) explain the kinds of systems Doc Holiday can read from or write to.

## The Library and instructions

The Library is the organization-wide collection of editable guidance.
[The Library](./e1-the-library.md) keeps that shared direction visible for every Publication in the Organization.
Each instruction is one entry in the Library, and it can apply to every Publication or only to selected Publications.

## Work History

Work History is the record of one documentation request from the first trigger to the final result.
Each entry belongs to one Publication and one Source.
A request can show stages such as Running, Ready for Review, Open, Needs Attention, Merged, Closed, or Cancelled.
[Work History](./f4-work-history.md) keeps that path visible when the request needs another pass or another reply.

Something happens in a Source, Doc Holiday turns that change into reviewed documentation in a Publication, and the Library guides the writing.
Work History records that result, so the vocabulary stays connected from input to outcome.

---

<!-- doc-holiday-watermark -->
<p align="center">
  <a href="https://doc.holiday">
    <img alt="Doc Holiday logo" src="https://doc.holiday/assets/docs-by-doc-holiday.png" width="200">
  </a>
</p>
<p align="center">Docs authored by <a href="https://doc.holiday">Doc Holiday</a></p>
