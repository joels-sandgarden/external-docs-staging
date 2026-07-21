# Concepts

Doc Holiday uses a small set of shared words to describe where documentation belongs, where source information comes from, and how work moves from request to result. Read this page first so the rest of the documentation can use those words consistently.

## Organization

An Organization is the top-level account that owns the rest of the workspace. It holds Publications, Sources, and the Library, so every part of the product belongs to one place at the same time. That hierarchy keeps ownership simple: every child concept starts inside one Organization before it takes on its own role.

Organization sits above the other concepts rather than beside them. When a reader sees a Publication, a Source, or an instruction, each one already has an Organization behind it.

## Publication

A Publication is the set of documentation that Doc Holiday keeps current. It is the thing the product maintains over time, so it reaches beyond a single page and includes whatever content belongs together as one body of documentation. Readers can think of it as a maintained scope rather than a single file.

A Publication points at Sources instead of owning them. That relationship matters because the Publication describes what Doc Holiday should write and where it should look for the information that drives that writing.

One Organization can hold many Publications, and each Publication can draw from the Sources that matter for that documentation set. The publication list in the app reflects that shape: a Publication is a maintained destination, not a loose collection of pages.

## Sources

Sources are the connected systems Doc Holiday works with. Some Sources give Doc Holiday material to read, some also accept the documentation it writes, and some serve as a place for updates and notifications to travel through the same workspace. That means the same word covers both the information stream and the places that surface progress to a team.

The product supports three roles here. A git repository Source can be both a place Doc Holiday reads from and a place it writes to. A context Source only supplies background information. Slack fills the notifier role, so it helps carry signals and updates without becoming the main documentation destination.

A Publication points to the Sources it depends on, and the Sources in turn explain what Doc Holiday can verify for that Publication. That keeps the relationship clear: the Publication defines the documentation set, while the Sources provide the surrounding truth it uses to keep that set current. [Sources](/c1-sources.md)

That is why source selection matters as soon as a Publication takes shape.

## The Library and instructions

The Library is the organization-wide collection of editable guidance. It gives the whole workspace a shared writing voice, and it keeps repeated guidance in one place instead of scattering it across individual Publications. That lets one Organization keep a consistent tone while still allowing different Publications to use different guidance when they need it.

An instruction is one entry in the Library. It can apply everywhere or only to selected Publications, which lets one piece of guidance shape all documentation or just the work for a specific Publication.

The Library influences how Doc Holiday writes, not what it invents. A Publication can inherit guidance from the Library, so the same Organization can keep documentation style aligned while still allowing different Publications to use their own instructions when needed. [the Library](/e1-the-library.md)

## Work History

Work History is the record of one documentation request from first signal to final result. Each entry belongs to one Publication and one Source, so it shows exactly which documentation set and which connected system the work came from. That scope lets the record stay specific without losing the bigger story of how the request moved.

A Work History entry follows the request as it moves through its stages. It opens when something triggers the work, moves through review and revision, and then settles into a result such as finished, closed, cancelled, or waiting on more attention. The record can move from open to review to revised to complete, or it can stop early if the request closes, gets cancelled, or needs attention.

Work History shows the current stage of the request rather than a status chosen by hand. That makes it the clearest place to understand what Doc Holiday is doing right now for a specific Publication and Source. [Work History](/f4-work-history.md)

Something happens in a Source, Doc Holiday turns that change into reviewed documentation in a Publication, the Library guides the writing, and Work History records the result. The words describe one path from a source change to maintained documentation and a visible record of the work.