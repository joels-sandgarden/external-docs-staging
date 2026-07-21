# Prompting guide

Doc Holiday gives the best result when your standing instructions and your one-off request point to the same outcome. The Library, the Publication, and Work History are the shared parts of that model; [Concepts](/a3-concepts.md) names them.

## Standing instructions (the Library and Publication configuration) govern every run

The Library holds reusable instructions, and the Publication's configuration can carry the same kind of guidance for one Publication. Use it for durable choices such as a reusable voice rule, a standard wording pattern, or a scope boundary that should apply every time. When a Publication points to a Library instruction, Doc Holiday follows that shared guidance before the inline Publication text.

## Per-request prompts govern one run

The request controls one Work History entry. Use it for the exact change that matters now. For example, a request thread can say, “Keep the existing API-key section unchanged.” That instruction shapes this run and nothing else.

When instructions conflict, the order stays fixed: defaults come first, Publication instructions and the Library come next, and your request comes last. Inside one request, the latest instruction wins, so a later correction can narrow or replace an earlier ask.

```
[CLAUDE_SECTION: golden-rule-and-examples]
```

Mini-map:
- [Writing requests](/p2-writing-requests.md)
- [Writing style guides](/p3-writing-style-guides.md)
- [Writing planning instructions](/p4-writing-planning-instructions.md)
- [Prompt patterns](/p5-prompt-patterns.md)

See [the Library](/e1-the-library.md) and [Request work from the app](/f2-request-work-in-the-app.md).