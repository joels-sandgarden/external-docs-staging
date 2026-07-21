# Writing style guides

A style-guide instruction makes everything Doc Holiday writes sound like your team wrote it. It applies to every run for the [Publications](/d1-publications.md) it's linked to — which makes it the right home for durable preferences, and the wrong home for one-off scope (that's a [request](/p2-writing-requests.md)).

## What belongs in a style guide

Four kinds of rules earn their place:

**Audience.** Who the reader is and what they can be assumed to know. This is the highest-leverage rule you can write, because it decides everything downstream — vocabulary, depth, what needs explaining.

> Write for support engineers with moderate technical proficiency. Don't assume they know git internals; do assume they know our product's UI.

**Altitude.** What kind of writing each part of your docs is — and what it must never turn into.

> How-to pages are numbered steps to one outcome; never mix conceptual background into them. Link to concept pages instead.

**Voice.** The mechanical rules: person, tense, banned words.

> Second person, present tense, active voice. Never use: simply, easily, powerful, seamless. Never start a sentence with a gerund.

**Structure.** The shape your site requires — heading conventions, required sections, front matter your site generator needs.

> Every page opens with one sentence saying who it's for. H2 for sections; never H1 in the body. End how-to pages with a "Verify" step.

## A compact example

A real style guide can be fifteen lines. This one is a working shape to adapt:

```
# Acme docs style

## Audience
- Readers are Acme administrators; comfortable with our dashboard, not with our codebase.

## Voice
- Second person, present tense, active voice.
- Plain words. Banned: simply, easily, seamless, robust, leverage.
- Bold exact UI labels: select **Settings**, then **API Keys**.

## Structure
- One H1 (the title). H2 sections. No H4 or deeper.
- How-to pages: numbered steps, one action per step, expected result after each.
- Every page ends with a "Next" link to one related page.

## Rules
- Never document features behind feature flags.
- Prices and plan names come from the pricing page, never from code.
```

Every line is checkable — a reviewer (human or Doc Holiday's own review pass) can point at a sentence and say which rule it breaks. That's the test of a good rule.

## Anti-patterns

- **Contradictions.** "Be concise" plus "be comprehensive" makes every run a coin flip. Pick the default; let requests override per page.
- **Novel-length guides.** Fifty rules dilute each other. Ten rules that always apply beat fifty that sometimes do.
- **Uncheckable vibes.** "Make it engaging" gives the writer nothing to obey and the reviewer nothing to enforce. Convert taste into mechanics: sentence length, banned words, required sections.
- **Scope rules in disguise.** "Only write release notes to /changelog.md" is a planning rule — it belongs in [planning instructions](/p4-writing-planning-instructions.md), where its blast radius is explicit.

## Iterate from output

Write a modest guide, run real work, then read the output asking one question: *what rule would have prevented the thing I just fixed?* Add that rule; delete rules that never fire. Three cycles of this beats any style guide written in advance.

## Next

Link your style guide to publications via [the Library](/e1-the-library.md), scope planning behavior with [planning instructions](/p4-writing-planning-instructions.md), or steer a single run with [request craft](/p2-writing-requests.md).
