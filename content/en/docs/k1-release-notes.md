---
title: Release Notes
url: "docs/release-notes"
description: "User-visible changes to Doc Holiday, newest first."
---

## 2026-07-24

### 🚀 New Features

- **Add Concepts overview**
  - The docs now define the shared vocabulary used across core product concepts.
- **Clarify Publication scope**
  - The docs now explain how Publications organize documentation work.
- **Explain Source roles**
  - The docs now show how Sources provide context and receive documentation updates.
- **Define Work History lifecycle**
  - The docs now explain how Work History tracks a request from start to finish.
- **Update Source type references**
  - The docs now list the main Source types more clearly.
- **Launch GitHub setup guide**
  - The docs now walk through connecting GitHub and starting a first workflow.
- **Add GitLab setup guide**
  - The docs now cover connecting GitLab and using it as a Source.
- **Document Bitbucket setup guide**
  - The docs now explain how to connect Bitbucket as a Source.
- **Guide first Publication onboarding**
  - The docs now guide new teams through setting up a first Publication.
- **Configure OpenAI key setup**
  - The docs now explain how to add the OpenAI key needed for content generation.
- **Explain Confluence and Jira setup**
  - The docs now cover connecting Confluence and Jira for added context.
- **Expand Linear setup**
  - The docs now show how to connect Linear and use it in a workflow.
- **Cover Google Drive setup**
  - The docs now explain how to connect Google Drive as a Source.
- **Map cloud storage setup**
  - The docs now describe how to connect cloud storage for source content.
- **Improve Manage Connections**
  - The docs now make connection management easier to follow.
- **Refine Manage Publications**
  - The docs now make publication management clearer.

### ✨ Enhancements

- **Update trigger and event types**
  - The docs now describe available trigger and event types more clearly.
- **Expand Work History API reference**
  - The API reference now gives clearer details for Work History lookups.
- **Refresh Users API reference**
  - The API reference now reflects the latest user information.
- **Introduce Bedrock GPT-5.6 routing**
  - The `bedrock-gpt-5.6` path now sends Bedrock-capable GPT tasks through AWS Bedrock with GPT-5.6 Luna and the matching prompt while keeping the default GPT-5.4 path unchanged.
- **Add Anthropic BYOK support**
  - Anthropic keys can now route inference to Claude models with the expected timeout behavior.
- **Route the annotator through Bedrock GPT-5.6**
  - When `bedrock-gpt-5.6` is enabled, the annotator now uses GPT-5.6 Terra with its dedicated prompt instead of the default OpenAI model.
- **Broaden Gemini BYOK support**
  - Gemini API keys can now power BYOK requests with model equivalents mapped automatically when OpenAI is unavailable.
- **Append attribution watermarks to edited markdown**
  - OSS-tier markdown files edited during a director step now receive a single attribution footer, and later passes do not add a duplicate footer.
- **Support Groq BYOK routing**
  - Groq keys can now route inference through Groq while avoiding unsupported request fields and compaction behavior.
- **Refine writer Bedrock GPT-5.6 settings**
  - When `bedrock-gpt-5.6` is enabled, the writer now uses GPT-5.6 Terra with matching prompt, reasoning, and compaction settings instead of the default configuration.
- **Extend explorer Bedrock GPT-5.6 coverage**
  - When `bedrock-gpt-5.6` is enabled, the Explorer agent now uses GPT-5.6 Terra with Bedrock session settings and a dedicated prompt instead of the default OpenAI path.
- **Direct the director through Bedrock GPT-5.6**
  - When `bedrock-gpt-5.6` is enabled, the Director now uses GPT-5.6 Terra with a dedicated prompt and client-side compaction for Bedrock sessions.
- **Align model selection with prompt templates**
  - Annotator, Director, Explorer, Merge Summarizer, and Writer now resolve their model choice and prompt from the same shared binding.
- **Enable Cerebras BYOK routing**
  - Cerebras keys can now route inference through the Cerebras-backed model with provider-specific request handling.

### 🐛 Bug Fixes

- **Limit feature flag context to dashboard pages**
  - Feature flag context now initializes only for dashboard routes instead of every page in the app.
- **Reduce GPT-5.6 reasoning effort**
  - Director, Explorer, and Writer now use Medium reasoning effort with GPT-5.6 Terra instead of High.

### 💼 Known Issues

- **Refresh Go dependencies**
  - Builds now use the refreshed dependency graph and regenerated vendored code after the July dependency update.

## 2026-07-17

### 🚀 New Features

- **Use source-specific triggers**
  - Publications now react only to the events configured for each source.

### ✨ Enhancements

- **Link completion comments to Work History**
  - When background tasks finish without opening a pull request, completion comments now point to the related Work History entry.

### 🐛 Bug Fixes

- **Treat GitLab 404s as not found**
  - Downloads and webhook health checks now report missing GitLab resources more accurately instead of surfacing a generic failure.
- **Anchor review comment edits within lines**
  - Review comment edits now stay pinned to the intended lines instead of deleting surrounding content.
- **Skip deleted publications in access lookup**
  - Deleted publication records no longer appear when Doc Holiday loads user access.

## 2026-07-06

### 🚀 New Features

- **Open conversation feedback to authenticated users without roles**
  - Authenticated users without roles can now open conversation feedback.
- **Allow comments on staged Work History messages**
  - Staged Work History messages can now receive comments when they were blocked before.

### ✨ Enhancements

- **Add the required Slack scope**
  - Slack installation now asks for the additional `groups:read` scope.

### 🐛 Bug Fixes

- **Clarify instruction link audit logs**
  - Instruction link entries now read more clearly in the audit log.
- **Delay completion status until background work finishes**
  - Completion status no longer appears before work finishes.

## 2026-06-26

### 🚀 New Features

- **Open files in full-screen review mode**
  - The Files tab can now open a single file in a full-screen overlay with previous and next navigation.
- **Switch the Files tab to a present-state view**
  - The Files tab can now show the current file contents without the diff presentation while keeping comment placement intact.
- **Drag the comment marker to select a range**
  - The comment anchor now supports drag selection across multiple lines in the Files tab.
- **Resolve Linear comment authors**
  - Linear comments and issue creators now show profile names, display names, or email addresses instead of UUIDs.
- **Create publication sharing notifications**
  - Publication sharing now records in-app notifications so recipients can review shared access inside the app.
    
### ✨ Enhancements

- **Add a Files tab return link for anchored messages**
  - Anchored messages in Work History now provide a direct way back to the related file.
- **Displayed created and updated comment times**
  - Edited comments now show an updated timestamp, and a hover tooltip reveals the original created time.

### ⚠️ Breaking Changes

- **Update Doc Holiday terminology**
  - The dashboard, SDK, and backend APIs now use publication terminology and publication endpoints across the product.

### 🐛 Bug Fixes

- **Jump to the selected conversation page**
  - Work History now opens deep-linked conversations on the correct page and scrolls the selected row into view.
- **Preserve comment mode across rerenders**
  - The Work History comment composer now keeps the chosen mode while the same conversation remains open.
- **React only to create webhooks**
  - Linear issue webhooks now trigger reactions only on create events, which avoids duplicate downstream processing.
- **Log successful eyes reactions**
  - Doc Holiday now records a clear log line when it successfully adds the eyes acknowledgment reaction.
- **Fixed cancelled progress updates**
  - Cancelled requests now still update the posted progress comment instead of leaving it stuck.
- **Wrapped audit log cells**
  - Long audit log values now wrap onto multiple lines, keeping the event, object name, timestamp, and user email columns from overlapping.

## 2026-06-19

### 🚀 New Features

- **Provide shareable Jira Application installation links**
  - The Jira Application install flow now supports link sharing for Site Admins not provisioned within Doc Holiday.
- **Select a Linear team during connection setup**
  - Linear connections now support team selection during configuration.

### ✨ Enhancements

- **Sort instruction lists by name or last updated**
  - Instruction lists now remember the selected sort order.
- **Show global instructions in the library list**
  - Global instructions now appear in the library list.
- **Search doc type dropdowns during bulk attach**
  - Doc type dropdowns now support search during bulk attach.
- **Style and formatting guidance**
  - Style and formatting guidance now appears in publication editors.
- **Mark attached instructions as In Use**
  - Attached instructions now show an `In Use` label.
- **Display library badges for linked instructions**
  - Linked items now show a library badge.
- **Keep publication editors open after save**
  - Publication editors stay open after save.
- **Separate style and formatting edits from output checkboxes**
  - Style and formatting edits now appear apart from the output checkboxes in publication editors.
- **Require non-empty instruction content**
  - Saved instructions now require content before they can be stored.
- **Block duplicate global instruction names and types**
  - The library now rejects duplicate global instruction name and type combinations.
- **Preserve style and formatting context when saving**
  - Saving to the library now keeps the correct style and formatting context.
- **Rename Atlassian Forge to Atlassian Application**
  - Atlassian Forge now appears as Atlassian Application.
- **Rename Jira connection labels**
  - Jira connections now use `Jira Read-Only` and `Jira Project`.
- **Clarify connection toast feedback**
  - Connection toasts now show clearer setup and validation states.

## 2026-06-12

### 🚀 New Features

* **Added open pull request interactions**
  * Work History now lets users send messages, comments, and file edits while a conversation is tied to an open pull request.
* **Released Jira-based issue triggers**
  * Atlassian app-based Jira connections can now trigger work in Doc Holiday.
* **Introduced "Send to Doc" in Jira comment menus**
  * Comment dropdowns in Jira now include a "Send to Doc" action for individual comments.
* **Executed background tasks in batches**
  * Background tasks now process merge batches asynchronously until the work is complete.
* **Display merge metadata in Work History**
  * Merged conversations now show who merged the request and when the merge happened.

### ✨ Enhancements

* **Restored type specific placeholders**
  * The publication form now shows type specific guidance again and uses the selected instruction type to choose placeholder text.
* **Improved scrolling when applying instructions**
  * The interface now scrolls newly attached publication cards and the bulk attach form into view automatically.
* **Separated style and formatting controls from output options**
  * Style and formatting instruction editing now appears apart from the output checkboxes in the publication form.


## 2026-06-05

### 🚀 New Features

* **New permission levels** 
  * People provisioned in the Doc Holiday can now be set as admins or users.
* **New role types** 
  * Users can now be set as reviewers (read and make edit suggestions) or writers (full edit permissions), per Publication.
* **User permissions set on invite**
  * Admins can set invited folks to be either admins or users on invite.
    
### ✨ Enhancements

* **Expand publication editing for writers**
  * Writers with publication access can edit publications, while reviewers have view-only access.
* **Alphabetize user and invitation lists**
  * User lists are now sorted alphabetically.
* **Improve settings page speed**
  * Settings pages now load faster.

### 🐛 Bug Fixes

* **Fix sign out routing**
  * Sign out now returns people to the sign in page more reliably instead of leaving them on a logout screen.
* **Correct documentation URL validation**
  * Documentation connections now reject invalid URLs more consistently in both the form and the saved configuration.

Older entries: [Release notes archive](./k1b-release-notes-archive.md)


---

<!-- doc-holiday-watermark -->
<p align="center">
  <a href="https://doc.holiday">
    <img alt="Doc Holiday logo" src="https://doc.holiday/assets/docs-by-doc-holiday.png" width="200">
  </a>
</p>
<p align="center">Docs authored by <a href="https://doc.holiday">Doc Holiday</a></p>
