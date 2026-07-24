# Plan and Generate Docs with Skills

The Doc Holiday plugin adds three **skills** to your agent. Together they take a codebase from "no docs" to a planned, generated, illustrated documentation site — the same journey the [Prompting guide](./p1-prompting-guide.md) describes by hand, driven by your agent instead.

Each skill runs inside your agent, reads your code, and writes Markdown you review. They are designed to be used in order.

## 1. Define the site map

**`defining-the-documentation-site-map`** scans your source and proposes the information architecture: every page classified by the [Diátaxis](https://diataxis.fr) framework — tutorial, how-to, reference, explanation — with a per-page brief and a hierarchy diagram.

It emits two files:

- `DOCS_SITE_MAP.md` — the annotated page tree, a reconciliation note against any existing structure, a Diátaxis-balance check, and a coverage-gaps list.
- `DOCS_CONTENT_PLAN.md` — one brief per page: mode, audience, the question it answers, an outline, and the **source of truth in the code** the page is reconciled against.

Ask your agent: *"Define the documentation site map for this project."*

## 2. Write the prompts

**`writing-doc-holiday-prompts`** turns that plan into the actual Doc Holiday instructions. For every page it writes a ready-to-run `@doc.holiday` create prompt and a matching `update` prompt — each carrying the page's Diátaxis mode, scope, and target section — plus reusable [Library](./e1-the-library.md) entries for shared voice and per-mode style.

It emits:

- `DOC_HOLIDAY_PROMPTS.md` — the ordered, copy-paste prompt set, grouped to match the site map.
- `DOC_HOLIDAY_INSTRUCTION_LIBRARY.md` — the proposed Library entries and which slots each attaches to.

The skill writes the *prompts*, not the pages — Doc Holiday writes the pages from them. See [Writing requests](./p2-writing-requests.md) and [Writing style guides](./p3-writing-style-guides.md) for the craft these prompts encode.

Ask your agent: *"Write the Doc Holiday prompts for this site map."*

## 3. Capture screenshots

**`capturing-documentation-screenshots`** drives a browser to capture real product-UI screenshots for the pages that need them, crops out chrome and personal data, and wires the images into the docs. For shots it can't take itself — terminal output, an editor view, a native dialog — it wires the image path in first and hands you an exact capture list.

Ask your agent: *"Capture the screenshots for these docs."*

## How this fits the plugin's tools

The skills plan and write; the plugin's [MCP tools](./j12-mcp-tools.md) drive the service — submitting the prompts and tracking each request through review. See [Coding agents](./g3-coding-agents.md) for the two ways an agent connects, and [Request docs via the API](./g7-request-docs-api.md) for the no-plugin path.
