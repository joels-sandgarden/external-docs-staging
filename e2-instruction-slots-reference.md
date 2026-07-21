# Instruction slots reference

Use this page to look up the instruction slots that appear in the Library and Publication settings.

## Slot reference

| Slot | What it governs | When it is applied | Typical use |
| --- | --- | --- | --- |
| documentation | Long-form user documentation | When Doc Holiday writes or updates a page in a Publication | Tone, structure, and page shape |
| release notes | Release note content | When Doc Holiday writes release notes for a release | Audience, summary length, and release framing |
| changelog | Changelog entries | When Doc Holiday updates the changelog for shipped changes | Entry format and release grouping |
| commit | Commit messages | When Doc Holiday creates or rewrites a commit message | Message style and required prefixes |
| planning | Planning notes | When Doc Holiday drafts planning content for a work request | Scope, ordering, and review notes |

## How linking works

An instruction can stay global, or it can link to one or more Publications. Multiple instructions can share the same slot. When that happens, Doc Holiday applies all linked instructions for that slot together.

## Precedence

Library instructions take precedence over inline Publication instructions. When both exist for the same slot, Doc Holiday uses the Library-linked instruction first and falls back to inline text only when no linked instruction applies.

## See also

- [The Library](/e1-the-library.md)
- [Writing style guides](/p3-writing-style-guides.md)