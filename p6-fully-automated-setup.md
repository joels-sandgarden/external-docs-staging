# Fully automated setup

Everything on this page happens once. Connect your repositories, create one Publication, turn on triggers, and paste in the two standing instructions below. From then on Doc Holiday reacts to what ships on its own: merged pull requests and releases go in; documentation updates and release notes come out as pull requests for your team to review. Nobody has to remember to ask.

To drive Doc Holiday by hand instead, start with the [Quickstart](/b1-quickstart.md).

## The setup

1. **Connect your repositories.** The code repository is what Doc Holiday reads; the docs repository is where it writes. Follow [Connect GitHub](/b2-connect-github.md), [Connect GitLab](/b3-connect-gitlab.md), or [Connect Bitbucket](/b4-connect-bitbucket.md).
2. **Create one Publication.** Put the code repository in **Inputs**, set the docs repository as the destination, and under **Write:** check **Documentation** and **Release Notes**. Follow [Create your first publication](/b5-create-your-first-publication.md); the outputs are explained in [Output types](/d3-output-types.md).
3. **Turn on triggers.** On the Publication form, under **Inputs**, select **Add Triggering Event**, choose the code Source, and enable **Pull Requests** (GitLab Sources show **Merge Requests**) and, where the Source supports it, **Releases**. Per-Source support is tabulated in [Configure triggers](/d2-configure-triggers.md).
4. **Paste in the two standing instructions below.** The planning instructions go in the Publication's **Writing Instructions** slot; the style guide attaches as **Style & Formatting** to the Documentation and Release Notes outputs. Add them inline on the Publication, or link them from [the Library](/e1-the-library.md) to reuse them across Publications.
5. **Set the Slack notifier** so merged work announces itself in a channel your team reads: on the Publication form, set **Notify** to a Slack Channel source. Follow [Slack notifications](/g4-slack-notifications.md).

## The full prompts

Both blocks are complete and ready to paste; adapt the bracketed parts to your site. The craft behind them is in [Writing planning instructions](/p4-writing-planning-instructions.md) and [Writing style guides](/p3-writing-style-guides.md).

**Planning instructions** — the Publication's **Writing Instructions** slot:

```
- When a merged pull request changes existing behavior, update the affected
  pages rather than creating new ones. Create a new page only for a genuinely
  new capability.
- Plan one page per user-facing feature area — never one page per API
  endpoint, never one page per code module.
- Only document behavior visible to users. Ignore internal tooling, internal
  mechanisms, and anything behind a feature flag.
- New guides go under [/docs/]. Whenever a page is added, add it to the
  [sidebar file] in the same piece of work.
- Release notes live in [/changelog/], one file per release, newest first.
- Cross-link between pages instead of repeating material.
```

**Style guide** — attach as **Style & Formatting** to the Documentation and Release Notes outputs:

```
# [Product] docs style

## Audience
- Readers are [product] administrators; comfortable with the dashboard, new
  to the internals.

## Voice
- Second person, present tense, active voice.
- Plain words. Banned: simply, easily, seamless, robust, leverage.
- Bold exact UI labels: select **Settings**, then **API Keys**.

## Structure
- One H1 (the title). H2 sections. No H4 or deeper.
- How-to pages: numbered steps, one action per step, expected result after
  each.
- Every page ends with a "Next" link to one related page.

## Release notes
- Group by: New features, Improvements, Fixes.
- One line per change, written for customers — describe what they can do now.
- Skip internal-only changes.
```

## Optional: a scheduled sweep

Triggers react to events. To also catch drift on a fixed rhythm, run the [GitHub Action](/g1-github-action.md) on a schedule:

```yaml
name: Weekly docs sweep
on:
  schedule:
    - cron: "0 9 * * 1"

jobs:
  docs:
    runs-on: ubuntu-latest
    steps:
      - uses: sandgardenhq/doc-holiday-action@v3
        with:
          api-token: ${{ secrets.DOC_HOLIDAY_TOKEN }}
          body: >
            Review the documentation against what shipped recently and update
            any page that no longer matches current behavior.
          commits-count: 100
```

`commits-count: 100` scopes each run to the most recent 100 commits — size it to your merge rate. Creating the `DOC_HOLIDAY_TOKEN` secret and the full input list are covered in [GitHub Action](/g1-github-action.md).

## What arrives, and what stays human

When a pull request merges or a release publishes, a new entry appears in [Work History](/f4-work-history.md): Doc Holiday explores what changed, updates the affected pages or writes the release notes, and opens a pull request in your docs repository. Your team reviews and merges it like any other change — Doc Holiday never writes to your repositories without an approved pull request ([Security and data handling](/h5-security-and-data-handling.md)).

One maintenance habit is worth keeping: when review keeps fixing the same kind of thing, add the rule that would have prevented it to your style guide. [Writing style guides](/p3-writing-style-guides.md) calls this iterating from output.

## Verify

1. Merge a small pull request in the code repository.
2. Open [Work History](/f4-work-history.md) and confirm a new entry appears for the Publication.
3. Review the pull request Doc Holiday opens in your docs repository, then merge it. If you set the Slack notifier, the message arrives after the merge.

## Next

Per-Source trigger details are in [Configure triggers](/d2-configure-triggers.md); tune coverage rules with [Writing planning instructions](/p4-writing-planning-instructions.md); for the occasional one-off request, use [Prompt patterns](/p5-prompt-patterns.md).
