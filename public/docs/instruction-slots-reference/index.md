# Instruction Slots Reference


Use this page to look up where each instruction slot appears on a Publication and what it controls.

## Slot reference

| Publication slot | API value | Instruction shown in the app | What it controls |
| --- | --- | --- | --- |
| Documentation | `documentation` | Style & Formatting | Style and formatting for documentation pages Doc Holiday writes. |
| Release Notes | `releaseNotes` | Style & Formatting | Style and formatting for release notes. |
| Changelog | `changelog` | Style & Formatting | Style and formatting for changelog entries. |
| Writing Instructions | `planning` | Writing | What Doc Holiday plans to work on, including which files matter and where outputs go. |
| Commit Instructions | `commit` | Commit | How Doc Holiday opens pull requests, including titles, commit messages, PR body, and branch naming. |

You can attach one Style & Formatting instruction to the Documentation, Release Notes, and Changelog slots at the same time.

## Resolution

When more than one Library instruction is attached to the same slot, Doc Holiday follows them in the order arranged on the Publication. The Publication’s inline text for that slot applies only when no Library instruction is attached.

## See also

- [The Library](./e1-the-library.md)
- [Writing style guides](./p3-writing-style-guides.md)
