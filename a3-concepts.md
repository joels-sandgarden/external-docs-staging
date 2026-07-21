# Concepts

Doc Holiday uses a shared vocabulary to describe where documentation belongs, where source information comes from, and how work moves from request to result. Read this page first so the rest of the documentation can use those words consistently.

## Organization

An Organization is the top-level account for a workspace. It owns the Publications, Sources, and the Library, so every other concept starts inside one shared boundary. That ownership keeps settings, content, and guidance from drifting apart when more than one team uses the product.

Organization sits above the rest of the model, so every Publication, Source, and instruction already belongs somewhere before it takes on its own role. That makes the hierarchy easy to read: one Organization provides the home, and the child concepts do the work inside it.

## Publication

A Publication is the body of documentation that Doc Holiday keeps current. It describes one maintained documentation set rather than a single page, so the same Publication can cover several pages or outputs when they belong together.

A Publication points at Sources instead of owning them. That relationship matters because the Publication defines what gets written, while the Sources define where the information comes from and where the finished work belongs. One Organization can hold many Publications, and each Publication can draw from the Sources it needs.

## Sources

Sources are the connected systems that feed Doc Holiday and receive its output. A Source can provide background information, accept documentation updates, or do both, depending on its role in a Publication. Git repositories let Doc Holiday work from the source material itself, context systems add surrounding detail, and other connected systems keep the work tied to the right place.

A Publication can point to more than one Source, which lets one documentation set combine code, context, and workflow signals. That keeps the roles clear: the Publication names the documentation set, and the Sources show what Doc Holiday can verify for it. [Sources](/c1-sources.md)

## The Library and instructions

The Library is the organization-wide collection of editable guidance [the Library](/e1-the-library.md). It gives the workspace a shared writing voice without forcing every Publication to use the same rules in the same way. An instruction is one entry in the Library, and it can apply to every Publication or only to selected ones.

The Library shapes how Doc Holiday writes, not what it invents. It keeps recurring guidance in one place, so an Organization can hold a consistent tone while still letting individual Publications rely on the instructions they need. That separation keeps the Library reusable and keeps each Publication focused on its own scope.

## Work History

Work History is the record of one documentation request from the first signal to the final result. Each entry belongs to one Publication and one Source, so the record shows exactly which documentation set and which connected system the work came from. That scope keeps the history specific while still showing the full path from request to review.

A Work History entry follows the request as it moves through its stages. It opens when something triggers the work, moves through review and revision, and settles into a result such as finished, closed, cancelled, or waiting on more attention. The entry always shows the current stage of the request rather than a status chosen by hand, which makes it the clearest place to see what Doc Holiday is doing right now. [Work History](/f4-work-history.md)

Something happens in a Source, Doc Holiday turns that change into reviewed documentation in a Publication, the Library guides the writing, and Work History records the result. That one flow keeps the vocabulary connected from input to outcome.