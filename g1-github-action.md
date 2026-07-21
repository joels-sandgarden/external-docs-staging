# GitHub Action integration

## What the action does

Doc Holiday's GitHub Action files a documentation work request through the Conversations API. Use it when CI should ask Doc Holiday to prepare documentation work on a schedule or after a release.

It fits scheduled jobs and release pipelines that should queue docs work without opening the app. Doc Holiday returns a result you review before it lands.

## Prerequisites

Create an API key in Doc Holiday **Settings → API Keys** and store it as the `DOC_HOLIDAY_TOKEN` repository secret. See [API key overview](/j1-api-overview.md) for background.

## Quick start

```yaml
name: Generate Documentation
on:
  release:
    types: [published]

jobs:
  docs:
    runs-on: ubuntu-latest
    steps:
      - uses: sandgardenhq/doc-holiday-action@v3
        with:
          api-token: ${{ secrets.DOC_HOLIDAY_TOKEN }}
          body: "Generate release notes for the latest release"
          releases-count: 1
```

## Inputs and outputs

Choose only one changeset specification type per run.

| Type | Inputs | Details |
| --- | --- | --- |
| Required | `api-token` | Required. |
| Required | `body` | Required. |
| Optional | `publication` | Publication ID or name. |
| Optional | `stage` | When `true`, work does not immediately open a pull request. |
| Optional | `labels` | Comma-separated labels. |
| Optional | `relevant-links` | Comma-separated URLs. |
| Changeset specification | `releases-count` | Release count. |
| Changeset specification | `time-range-start` + `time-range-end` | ISO 8601 timestamps. |
| Changeset specification | `commits-count` | Commit count. |
| Changeset specification | `commits-since-sha` | Start from one commit SHA. |
| Changeset specification | `commits-shas` | Comma-separated commit SHAs. |
| Changeset specification | `commits-start-sha` + `commits-end-sha` + `commits-include-start` | Commit range. |
| Changeset specification | `tags-start` + `tags-end` | Tag range. |

| Output | Description |
| --- | --- |
| `id` | Work request ID. |
| `status` | Job state, such as `requested`, `running`, `done`, or `errored`. |
| `branch` | Branch created for the work. |
| `output-url` | Link to the result. |

## Triggers vs CI

For event-based workflows, see [Configure triggers](/d2-configure-triggers.md). Use the GitHub Action when CI should start the request on a schedule or as part of a release pipeline.