# Prompting guide

Doc Holiday gives the best result when your standing instructions and your one-off request point to the same outcome. The Library, the Publication, and Work History are the shared parts of that model; [Concepts](/a3-concepts.md) names them.

## Standing instructions (the Library and Publication configuration) govern every run

The Library holds reusable instructions, and the Publication's configuration can carry the same kind of guidance for one Publication. Use it for durable choices such as a reusable voice rule, a standard wording pattern, or a scope boundary that should apply every time. When a Publication attaches Library instructions to a slot, Doc Holiday follows them in the order they are arranged on the Publication; inline Publication text applies when no Library instruction is attached to that slot.

## Per-request prompts govern one run

The request controls one Work History entry. Use it for the exact change that matters now. For example, a request thread can say, “Keep the existing API-key section unchanged.” That instruction shapes this run and nothing else.

When a request conflicts with standing instructions, the standing instructions win: Publication and Library instructions set the boundaries every run must respect, and a request works inside them. A request that asks for something the Publication rules out — an output type it does not write, a scope it excludes — will follow the Publication. To change the boundary, change the instruction; to change one run's work, change the request.

## The golden rule

Put durable preferences in instructions. Put one-off scope in requests.

A preference belongs in an instruction when you would repeat it on every request. "Never call anything 'simple' or 'straightforward'." "Write for operators, in second person." "Every how-to ends with a Verify section." Write these once and every run follows them.

Scope belongs in the request when it names this run's work: "Write a migration guide for the v2 auth change in `payments-service`." "Update `/docs/webhooks.md` for the new retry behavior; leave the signature section alone."

Two signs something is in the wrong lever:

- You keep pasting the same sentence into requests. Move it to an instruction — [Writing style guides](/p3-writing-style-guides.md) shows the shape.
- An instruction names a specific file or release. It will keep steering every future run long after that release ships. Make it a request instead.

Mini-map:
- [Writing requests](/p2-writing-requests.md)
- [Writing style guides](/p3-writing-style-guides.md)
- [Writing planning instructions](/p4-writing-planning-instructions.md)
- [Prompt patterns](/p5-prompt-patterns.md)

See [the Library](/e1-the-library.md) and [Request work from the app](/f2-request-work-in-the-app.md).