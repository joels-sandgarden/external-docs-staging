# GitLab Pipelines


This component lets you file a work request from a GitLab pipeline with a prompt, then review the generated documentation output before it lands in the docs repo.

## Prerequisites

1. Create an API key in Settings → API Keys. See [API keys](./j1-api-overview.md).
2. Add it to the GitLab project or group as a CI/CD variable named `DOC_HOLIDAY_TOKEN`.
3. Mark the variable `masked` and `protected`.

## Quick-start include

Use this include when the pipeline should send a prompt and produce a draft for review.

```yaml
include:
  - component: gitlab.com/sandgarden/doc-holiday-ci-job/generate-docs@1.0.0
    inputs:
      title: "Release notes for ${CI_COMMIT_TAG}"
      body: "Generate release notes from the latest commits"
      commits-count: 10
```

## Tag-based release example

Use this pattern when the pipeline runs from a release tag.

```yaml
generate-release-docs:
  stage: deploy
  rules:
    - if: $CI_COMMIT_TAG
  script:
    - !reference [.generate-docs, script]
  variables:
    INPUT_TITLE: "Release ${CI_COMMIT_TAG}"
    INPUT_BODY: "Release notes for ${CI_COMMIT_TAG}"
    INPUT_RELEASES_COUNT: "1"
```

## What else it supports

GitLab CI variable substitution such as `${CI_COMMIT_TAG}` and `${CI_PROJECT_NAME}` works in the component. It accepts the same changeset-specification inputs as the [GitHub Action](./g1-github-action.md): releases-count, time ranges, commit counts, SHAs, ranges, and tags. The same project also ships `load-jira-issues` and `load-linear-issues` companion components that extract issue links from commits and can feed them to `generate-docs`.

## CI versus triggers

Choose GitLab CI/CD when the work should start from a pipeline and the prompt belongs with the repo change. Choose triggers when the request should start from an event instead; see [Configure triggers](./d2-configure-triggers.md) for that path. Pick the entry point that matches how the team already works.
