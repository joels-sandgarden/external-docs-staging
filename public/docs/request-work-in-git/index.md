# Request Work in Git


Mention `@doc.holiday` in the thread you are already using. Doc Holiday starts the request there. Put `@doc.holiday` first or within the first few words, then describe the change.

## Where it works

- GitHub issue comments and pull request comments.
- GitHub pull request review bodies and pull request review comments.
- GitHub, GitLab, and Linear new issue bodies that mention `@doc.holiday` within the first few words.
- GitLab issue notes and merge request notes.
- Bitbucket pull request comments.
- Linear issue comments. If Linear is not connected yet, see [Connect Linear](./c4-connect-linear.md).

## What happens next

Doc Holiday reacts to your comment, replies in the same thread, and keeps the response with the request. Follow-up comments on the pull request Doc Holiday opened continue the same Work History entry. A second request on the originating issue gets a reply pointing you to that linked pull or merge request — make change requests there, or open a new issue for net-new work.

## Help shortcut

Use `@doc.holiday help` when a short reminder is enough. Doc Holiday returns inline usage help and examples.

## Example requests

On a pull request that changed behavior:

```text
@doc.holiday this PR renames the `timeout` config key to `request_timeout`.
Update /docs/configuration.md to match; leave the retries section alone.
```

On an issue asking for a missing page:

```text
@doc.holiday write a troubleshooting page for webhook delivery failures.
Cover signature mismatches and retry behavior; base it on webhooks/handler.go.
```

A follow-up comment on the pull request Doc Holiday opened, after reviewing the draft:

```text
@doc.holiday the example in the new page uses the v1 payload.
Switch it to the v2 shape from webhooks/payload.go.
```

Name the outcome and the page you want; when a file matters, give its path. [Writing requests](./p2-writing-requests.md) covers the craft in full.

## Verify

The request appears in [Work History](./f4-work-history.md).
