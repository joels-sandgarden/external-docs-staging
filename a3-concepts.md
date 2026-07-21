# Concepts

Doc Holiday uses a shared vocabulary to describe where documentation belongs, where source information comes from, and how work moves from request to result. Read this page first so the rest of the documentation can use those words consistently.

## Organization

An Organization is the top-level account for a workspace. It owns the Publications, Sources, and the Library, so every other concept starts inside one shared boundary. That ownership keeps settings, content, and guidance from drifting apart when more than one team uses the product.

Organization sits above the rest of the model, so every Publication, Source, and instruction already belongs somewhere before it takes on its own role. That makes the hierarchy easy to read: one Organization provides the home, and the child concepts do the work inside it. When a team adds a new Publication or Source, it still lands inside the same ownership model.

## Publication

A Publication is the maintained set of documentation that Doc Holiday keeps current for one area of the product, one topic, or one release surface that needs to stay up to date.
It names a body of content rather than a single page, which lets one Publication cover several related pages, outputs, or audiences without losing focus when the scope expands.
A Publication points at Sources instead of owning them, so it defines what the docs set covers while the Sources define where the information comes from and where the finished work belongs.

## Sources

Sources are the connected systems that feed Doc Holiday and receive its output, including places that supply background, places that hold the work, and places that do both for a Publication.
One Source can provide context for a Publication, another can accept documentation updates, and another can keep the publication tied to the system that matters most to the team.
A Publication points to Sources rather than owning them, so [Sources](/c1-sources.md) tell Doc Holiday what it can verify, what it can write, and how the finished work should appear.

## The Library and instructions

The Library is the organization-wide collection of editable guidance, and [the Library](/e1-the-library.md) keeps that shared direction visible for every Publication in the Organization without forcing identical behavior everywhere.
Each instruction is one entry in the Library, and it can apply to every Publication or only to selected Publications when a team needs a narrower rule for specific work.
The Library shapes how Doc Holiday writes by giving each Publication the same source of guidance while still letting it use the instructions it needs for its own subject matter and audience.

## Work History

Work History is the record of one documentation request from the first signal to the final result, so it preserves the path of a single piece of work from start to finish.
Each entry belongs to one Publication and one Source, which shows exactly which documentation set and which connected system started the work and why it matters there at review time.
A single entry opens when something triggers it, moves through review and revision, and settles into a result such as finished, closed, cancelled, or waiting for more attention; [Work History](/f4-work-history.md) keeps that path visible when the request needs another round of comments or another follow-up pass.

Something happens in a Source, Doc Holiday turns that change into reviewed documentation in a Publication, the Library guides the writing, and Work History records the result in one continuous loop.
This model keeps the vocabulary connected from input to outcome, so the rest of the documentation can stay consistent even when a request needs several passes before it settles.