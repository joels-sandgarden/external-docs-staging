# Publishing systems

Doc Holiday uses the **Publishing System** field to match a docs site with the site structure and writing conventions it expects. This page lists the available options, how the setting gets chosen, and what to do when the site does not fit a named system.

## Supported systems

These are the options shown in the **Publishing System** field.

| Label | Notes |
| --- | --- |
| None | Literal UI option for no selection. |
| Antora | Select for Antora sites. |
| Astro | Select for Astro sites. |
| Docusaurus | Select for Docusaurus sites. |
| Eleventy | Select for Eleventy sites. |
| Gatsby | Select for Gatsby sites. |
| Generic Markdown | Select for plain Markdown sites or as the fallback choice. |
| GitBook | Select for GitBook sites. |
| Hugo | Select for Hugo sites. |
| Jekyll | Select for Jekyll sites. |
| MadCap Flare | Select for MadCap Flare sites. |
| MkDocs | Select for MkDocs sites. |
| Next.js | Select for Next.js sites. |
| Nuxt | Select for Nuxt sites. |
| Sphinx | Select for Sphinx sites. |
| VuePress | Select for VuePress sites. |

## How Doc Holiday chooses a publishing system

The setting can come from two places: the **Publishing System** field on the source setup form, or automatic detection from signature files in the repository.

Automatic detection looks for files that identify a site generator. Examples include `docusaurus.config.js` or `docusaurus.config.ts` for Docusaurus, `mkdocs.yml` or `mkdocs.yaml` for MkDocs, `.vuepress/config.js` or `.vuepress/config.ts` for VuePress, and `antora.yml`, `antora.yaml`, `antora-playbook.yml`, or `antora-playbook.yaml` for Antora. Doc Holiday also checks `package.json` as a lower-confidence signal when no signature file gives a clear result.

## What it is used for

Doc Holiday uses the publishing system to understand a site’s structure and conventions when writing.

## Fallback guidance

If the site generator is not listed, or if no better match exists, choose `Generic Markdown`. Use `None` only as the literal UI option for no selection; it is not the recommended choice for an unrecognized site.

For publication setup and source selection, see [Publications](/d1-publications.md) and [Sources](/c1-sources.md).