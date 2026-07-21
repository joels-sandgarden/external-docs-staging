# Concepts

Doc Holiday uses a shared vocabulary to describe where documentation belongs, where source information comes from, and how work moves from request to result. Read this page first so the rest of the documentation can use those words consistently.

## Organization

An Organization is the top-level account for a workspace. It owns the Publications, Sources, and the Library, so every other concept starts inside one shared boundary. That ownership keeps settings, content, and guidance from drifting apart when more than one team uses the product.

Organization sits above the rest of the model, so every Publication, Source, and instruction already belongs somewhere before it takes on its own role. That makes the hierarchy easy to read: one Organization provides the home, and the child concepts do the work inside it. When a team adds a new Publication or Source, it still lands inside the same ownership model.

## Publication

A Publication is the body of documentation that Doc Holiday keeps current. It describes one maintained documentation set rather than a single page, so the same Publication can cover several pages or outputs when they belong together. That makes a Publication the unit of maintenance for a topic, product area, or release surface.

A Publication points at Sources instead of owning them. That relationship matters because the Publication defines what gets written, while the Sources define where the information comes from and where the finished work belongs. One Organization can hold many Publications, and each Publication can draw from the Sources it needs. This keeps scope clear when one documentation set depends on code, background material, and a separate destination for the final pages.

## Sources

Sources are the connected systems that feed Doc Holiday and receive its output. A Source can provide background information, accept documentation updates, or do both, depending on its role in a Publication. Git repositories let Doc Holiday work from the source material itself, context systems add surrounding detail, and other connected systems keep the work tied to the right place.

A Publication can point to more than one Source, which lets one documentation set combine code, context, and workflow signals. That keeps the roles clear: the Publication names the documentation set, and the Sources show what Doc Holiday can verify for it. A Publication may also use different Sources for reading and writing, so the same concept can cover both evidence and destination. [Sources](/c1-sources.md)

## The Library and instructions

The Library is the organization-wide collection of editable guidance, and [the Library](/e1-the-library.md) keeps that shared direction visible. It gives the workspace a common writing voice without forcing every Publication to use the same rules in the same way. An instruction is one entry in the Library, and it can apply to every Publication or only to selected ones. Because the Library stays editable, a team can refine guidance without rewriting each Publication by hand.

The Library shapes how Doc Holiday writes, not what it invents. It keeps recurring guidance in one place, so an Organization can hold a consistent tone while still letting individual Publications rely on the instructions they need. That separation keeps the Library reusable and keeps each Publication focused on its own scope. It also keeps the difference clear between the shared collection and the individual instruction inside it.

## Work History

Work History is the record of one documentation request from the first signal to the final result, so it preserves the path of a single piece of work from start to finish.
Each entry belongs to one Publication and one Source, which shows exactly which documentation set and which connected system started the work and why it matters there at review time.
A single entry opens when something triggers it, moves through review and revision, and settles into a result such as finished, closed, cancelled, or waiting for more attention; [Work History](/f4-work-history.md) keeps that path visible when the request needs another round of comments or another follow-up pass.

Something happens in a Source, Doc Holiday turns that change into reviewed documentation in a Publication, the Library guides the writing, and Work History records the result in one continuous loop.
This model keeps the vocabulary connected from input to outcome, so the rest of the documentation can stay consistent even when a request needs several passes before it settles.