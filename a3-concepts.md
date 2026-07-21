# Concepts

This page defines the shared vocabulary used throughout Doc Holiday’s documentation. Read it first when the terms around Organizations, Publications, Sources, the Library, and Work History start to blur together.

## Organization

An Organization is the top-level home for everything Doc Holiday keeps together. It gathers the Publications that Doc Holiday maintains, the Sources it can use, and the Library that holds shared guidance. That gives one team one place to manage the material that shapes every document request. An Organization sets the boundary for the rest of the model, so every other concept on this page belongs somewhere inside it.

## Publication

A Publication is the documentation destination Doc Holiday keeps current. It is the place where work lands after Doc Holiday reads the relevant Sources and prepares a reviewable result. A Publication can point at more than one Source, which lets one destination draw context from several places while still keeping a single focus. In practice, a Publication gives the work its purpose. It tells Doc Holiday which documentation set should change. A Publication sits under one Organization and gives the rest of the system a clear target.

## Sources

Sources are the connected systems Doc Holiday uses when it works on a Publication. A Source can play three different roles at a high level. It can be the repository Doc Holiday reads from and writes to, it can be a context system Doc Holiday only reads, or it can be a Slack connection that carries notifications. Git-based Sources let Doc Holiday work with a repository and a branch, while context Sources bring in background from places such as Notion, Confluence, Jira, Linear, Documentation, and Zendesk. That mix lets a Publication gather the right evidence without forcing every connection into the same shape. See [Sources](/c1-sources.md) for a deeper look at how these roles fit together. A Publication points at Sources rather than owning the information itself, so the Source list explains where the facts for a request come from.

## The Library and instructions

The Library is the organization-wide home for reusable writing guidance. Each instruction in the Library captures a piece of guidance that Doc Holiday can apply broadly or limit to specific Publications. That lets one Organization keep a shared voice and still tune individual Publications when they need different wording, structure, or scope. An instruction stays separate from the Publication it serves, so the same guidance can travel with the Organization and still fit more than one destination. See [the Library](/e1-the-library.md) for how the shared guidance is organized and applied.

## Work History

Work History is the record of one request from the moment it starts until it reaches a result. It shows what came in, what Doc Holiday did, and how the request ended. The lifecycle is simple: it opens, does its work, and settles into a result such as Ready for Review, Merged, or Closed. That makes Work History the place to look when you want to follow one request from start to finish. See [Work History](/f4-work-history.md) for the full page.

Taken together, these terms describe one path from source to page. Something happens in a Source, Doc Holiday turns it into reviewed documentation in a Publication, the Library keeps the guidance consistent, and Work History records the result.