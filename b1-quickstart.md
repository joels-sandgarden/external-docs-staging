# Quickstart

This quickstart takes a new user from sign-in to a merged Doc Holiday-written document.

1. After sign-in, open `app.doc.holiday`, select "Get started" on "Ready to get your docs in a row?", and continue to "Add Source(s)."
2. On the provider screen, select "GitHub", then choose "Install GitHub App". In the repository picker, use "Search repositories…", "Select all", and "Add Sources" to finish the connection.

> Need GitLab or Bitbucket instead? See [Connect GitLab](/b3-connect-gitlab.md) and [Connect Bitbucket](/b4-connect-bitbucket.md).

```
SCREENSHOT PLACEHOLDER: quickstart/onboarding-connect.png
```

3. Create the publication by filling in "What would you like to name this publication?", choosing "Which repositories are sources of changes for a single project or product?", pointing Doc Holiday at "Where should Doc Holiday write its words?", and turning on only "Documentation" under "What would you like Doc Holiday to write?". Leave "Release notes" and "Changelog" off, answer "What publishing system does {name} use?", and select "Create Publication". For the full setup, see [Create your first Publication](/b5-create-your-first-publication.md).

```
SCREENSHOT PLACEHOLDER: quickstart/publication-form.png
```

4. On "Verify your setup", select "Create Test Pull Request" until "View Pull Request" appears, then continue through "Choose your plan", "Add your AI provider key", and "Go to the Doc Holiday App". For the key step, see [Add your OpenAI key](/b6-add-your-openai-key.md).

5. In Work History, select "Create Work Request", then fill in "Publication" and "Description" with "Write a getting-started page for this project". Select "Submit Request" and wait for the "Work Request Created" success message. The entry then appears in Work History with the staged status "Ready for Review".

```
SCREENSHOT PLACEHOLDER: quickstart/create-work-request.png
```

```
SCREENSHOT PLACEHOLDER: quickstart/work-history-staged.png
```

6. Open the entry, select the "Files" tab, and review the draft. See [Review and revise](/f3-review-and-revise.md) for the next step. When it is time to publish, select "Open Pull Request". The dialog shows "Open Pull Request" with "Confirm" and "Cancel"; choose "Confirm" and merge the resulting GitHub pull request.

```
SCREENSHOT PLACEHOLDER: quickstart/open-pr-dialog.png
```

## Verify

The merged file is visible in the repository.

## Next

Next: [Review and revise](/f3-review-and-revise.md).