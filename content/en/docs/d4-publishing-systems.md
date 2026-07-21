---
title: Publishing Systems
url: "docs/publishing-systems"
description: "Supported docs frameworks and what Doc Holiday expects of a docs repo."
---

Doc Holiday uses the **Publishing System** field to match a docs site with the structure and conventions it expects. The page below lists the available options, how the setting gets chosen, and which fallback to use when the site does not fit a named system.

## Supported systems

These are the options in the **Publishing System** field.

| Label | Notes |
| --- | --- |
| None | Literal UI option for no selection. |
| Antora | Matches Antora sites. |
| Astro | Matches Astro sites. |
| Docusaurus | Matches Docusaurus sites. |
| Eleventy | Matches Eleventy sites. |
| Gatsby | Matches Gatsby sites. |
| Generic Markdown | Fallback for plain Markdown sites. |
| GitBook | Matches GitBook sites. |
| Hugo | Matches Hugo sites. |
| Jekyll | Matches Jekyll sites. |
| MadCap Flare | Matches MadCap Flare sites. |
| MkDocs | Matches MkDocs sites. |
| Next.js | Matches Next.js sites. |
| Nuxt | Matches Nuxt sites. |
| Sphinx | Matches Sphinx sites. |
| VuePress | Matches VuePress sites. |

## How Doc Holiday chooses a publishing system

The setting comes from the **Publishing System** field on the source/publication setup form, or from automatic detection of signature files in the repository.

Automatic detection looks for files that identify a site generator. Examples include `docusaurus.config.js` or `docusaurus.config.ts` for Docusaurus, `mkdocs.yml` or `mkdocs.yaml` for MkDocs, `.vuepress/config.js` or `.vuepress/config.ts` for VuePress, and `antora.yml`, `antora.yaml`, `antora-playbook.yml`, or `antora-playbook.yaml` for Antora. Doc Holiday also checks `package.json` as a lower-confidence signal when no signature file gives a clear result.

## What it is used for

Doc Holiday uses the publishing system to understand a site’s structure and conventions when writing.

## Fallback guidance

If the site generator is not listed, or if no better match exists, choose `Generic Markdown`. Treat `None` as the literal UI option for no selection, not the recommended choice for an unrecognized site.

For publication setup and source selection, see [Publications](./d1-publications.md) and [Sources](./c1-sources.md).