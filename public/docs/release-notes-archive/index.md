# Release Notes Archive


Entries prior to June 2026, preserved as published. Recent entries: [Release Notes](./k1-release-notes.md)

### 2026-05-29

#### ✨ Enhancements

* **Expand file previews for HTML and MDX**
  * File review now previews HTML alongside Markdown and recognizes `.htm` and `.mdx` files more cleanly.

#### 🐛 Bug Fixes

* **Fix retry status updates in Work History**
  * Retried turns now carry the conversation ID so Work History can switch the conversation back to a running state immediately.
* **Fixed error when saving sources without publishing system**
  * When creating/saving a source in the UI and selecting 'None' for the Publishing System, the source now saves without triggering an error.

### 2026-05-22

#### 🚀 New Features

* **Enhanced Bitbucket connections**
  * Connect Bitbucket at the workspace or project level with a simplified repo chooser and deeper support for linked files.
* **Link Doc replies back to comments**
  * Comments now show which request triggered each Doc reply and links to the related file.
* **Add Slack review notifications**
  * Publications and conversations can now send notifications to Slack when work is ready for review.
* **Post comments during automated review**
  * Automated review can now add Doc comments directly into the conversations where teams are discussing the work.

#### ✨ Enhancements
 
* **Improve file editing layouts and controls**
  * Scrolling in the UI editor keeps headers and toolbars aligned, save button tuned.
* **Refine comments and files tab**
  * The batch action stays during active work on comments tab and made the Files tab feel faster.
* **Polish conversation speed and status feedback**
  * Work History now reuses live conversation data more effectively and reduces extra fetching during work.
* **Internationalize time and print views**
  * Now use locale aware timestamps and printable reasoning pages use an explicit print action.
* **Expand review and notification controls**
  * Bitbucket review comments now support reactions that quickly confirm work.
* **Sharpen author presentation**
  * External comment links now use the author name when a source link exists.
* **Enhance image and preview stability**
  * Markdown previews now keep relative link images steadier and stop repeated retries after failures.

#### 🐛 Bug Fixes

* **Fix stacked comment loading behavior**
  * Stacked comments now measure and settle into place correctly without distracting entrance animations.
* **Correct draft comment visibility and focus**
  * New draft inputs now wait until they are visible before taking focus, the first draft card stays visible, and file level drafts still appear even when no other comments exist.
* **Resolve duplicate comment and reply collisions**
  * Replayed events and repeated external writes now update existing conversation comments instead of creating conflicting duplicates, and separate automations can still post their own replies.
* **Prevent duplicate Bitbucket pull requests**
  * Bitbucket workflows now reuse an existing open pull request for the same branch instead of opening a duplicate review request.
* **Align automated comments to accurate lines of code**
  * Automated comments now attach to the actual changed lines and use the active working branch so feedback lands in the right place.
* **Fix comment creation on older file revisions**
  * Comments created against older file versions now keep the intended file version and anchors more reliably.
* **Restore accurate message and action states**
  * The Open PR button stays disabled while a conversation is running and messages on Messages tab update immediately.

### 2026-05-15

#### 🚀 New Features

 * **Expand Slack connections and notifications**
   * Teams can now connect Slack workspaces and channels through dedicated Slack connection types, track setup, and send ready for review updates into selected Slack channels.
 * **Expand reasoning review in Work History**
   * Eligible conversations can now open stored reasoning in a dedicated Work History tab, refresh and download it, and use a print friendly view.
* **Edit files directly in Work History**
  * Work History now includes purpose built markdown and code editors with save and cancel controls for direct manual editing.
* **Create conversations through the legacy work_states route**
  * Older clients can still create conversations through `POST /api/v1/work_states/`, preserving compatibility while the product uses conversation terminology.
* **Publish an API specification**
  * Doc Holiday can now generate and expose a full API specification so API capabilities and compatibility routes are easier to inspect.
* **Suggest screenshots during writing**
  * Documentation workflows can now identify places where a screenshot would help and post an anchored request describing the missing visual.
* **Store conversation origins**
  * Conversations can now keep origin type and origin URL details so teams can trace where a request started.
* **Create organizations with built in roles**
  * New organizations now start with built in roles and a stored default role so access setup begins with consistent role scaffolding.
* **Delete organizations from orgctl**
  * Operators can now remove organizations from the command line, and successful deletions return `204 No Content` from the API.
* **Purge knowledge-base data from orgctl**
  * Operators can now delete an organization's stored knowledge-base data through a supported purge command.
* **List conversation diff history**
  * Conversation diff history can now be inspected in full so intermediate changes and their reasoning context are easier to follow.

#### ✨ Enhancements

* **Improve comment editing and deletion**
  * Users can now edit and delete comments with clearer action availability based on comment ownership.
* **Streamline file comment writing and review**
  * File comments now use multiline inputs, richer formatting, clearer labels, stronger visibility controls, linked message context, and a resizable review pane that stays easier to scan while files are open for editing.
* **Polish file comment states and controls**
  * Comment inputs now focus more reliably, draft range actions read more clearly, disabled and hidden controls behave more predictably, and avatars and quoted snippets use cleaner presentation.
* **Rename work states to conversations across the product**
  * The product now uses conversation terminology more consistently across clients, hooks, endpoints, and models.
* **Rename run logs to audit logs**
  * User facing log terminology now uses audit logs consistently across the product and API surfaces.
* **Show Ready for Review status wording**
  * The staged status label now appears as Ready for Review for clearer Work History status language.
* **Show Created By in Work History details**
  * Work History now displays who started a conversation under a Created By label.
* **Expose reasoning on conversations**
  * Conversations now store reasoning directly so Work History can show and refresh reasoning without relying on separate outputs.
* **Allow on demand conversation annotation**
  * Conversations can now be re annotated on demand through a dedicated API path and client hook.
* **Expand reasoning comments and rollout controls**
  * Conversations can now run annotation in the background, publish reasoning as anchored comments, hide older unsupported reasoning views, and roll out reasoning comments through feature flags.
* **Group rollout controls for comments and screenshots**
  * File comments and screenshot suggestions now share clearer feature flag coverage, and the interface hides comment behavior when those controls are off.
* **Support `.fltoc` documentation files**
  * Doc Holiday now recognizes `.fltoc` as a supported documentation file type.
* **Improve markdown editing and preview tools**
  * Manual editing now adds code block tools, block type controls, table sorting, a monospace code view, cleaner handling for frontmatter and links, and fuller markdown previews.
* **Broaden OpenAPI coverage**
  * The generated API specification now includes clearer endpoint summaries, visibility controls, generated YAML output, and documented Slack and compatibility routes.
* **Refine Slack setup and notifier behavior**
  * Slack setup now uses clearer notifier naming, stronger install and health handling, rollout controls for Slack connection types, clearer notification wording, and cleaner provider visuals and delete flows.
* **Improve comments source icons**
  * Comment source icons now use cleaner source type handling for more consistent display.
* **Show running status sooner after message send**
  * Work History now reflects active work immediately after a message is sent, improving response feedback.
* **Improve branch head checks across providers**
  * Git providers can now report the latest branch tip commit more reliably, including valid empty branch cases.
* **Improve GitHub pull request refresh matching**
  * Refresh flows can now find an existing GitHub pull request by branch when direct lookup fails.
* **Improve Bitbucket inline review anchors**
  * Bitbucket inline pull request comments now preserve file anchors and blob style fingerprints more like other providers.
* **Improve Bitbucket pull request comment validation**
  * Bitbucket review comment events now fail earlier when malformed so later handling paths stay simpler and safer.
* **Improve knowledge-base listing APIs**
  * Iterator based list methods now make large knowledge-base listings clearer about streaming versus full list behavior.
* **Improve knowledge-base failure logging**
  * Failure logs now include connection names and IDs so repository specific sync issues are easier to trace.
* **Make default role backfills more complete**
  * Existing organizations and existing users now receive default role IDs and default role membership more consistently.
* **Log default role failures instead of blocking users**
  * Default role assignment failures now fall back to diagnostic logging instead of interrupting the user flow.
* **Protect built in roles from deletion**
  * System defined roles now stay protected from accidental deletion.
* **Improve organization deletion safety**
  * Organization deletion now requires superuser access, protects the primary environment organization, and cascades through related users, connections, and automations.
* **React to Clerk organization deletion events**
  * Doc Holiday can now respond when Clerk reports that an organization has been deleted.
* **Filter expired install links out of app listings**
  * App listings now exclude expired invite links so only currently valid install links appear.
* **Standardize invite link naming**
  * Install link suffixes now use a shared random string helper for more consistent generation.
* **Expose richer agent connection context**
  * Agents now receive richer non secret connection metadata through XML configuration.
* **Clarify interactive request handling guidance**
  * Coordinator instructions now describe direct user messages, batch comments, file anchors, and related request fields more clearly.
* **Remove the old coordinator experiment flag**
  * The newer coordinator path is now the default without the earlier experiment branch.
* **Reduce noisy routine logging**
  * Less important errors now log at lower severity so routine failures create less noise.
* **Improve generated tool failure visibility**
  * Generated MCP tool failures now log with clearer warning and error details.
* **Improve screenshot workflow logging**
  * The writer now logs when screenshot suggestion mode starts and when a screenshot suggestion is posted.
* **Move screenshot handling into dedicated paths**
  * Screenshot suggestion handling now runs through a dedicated skill and handler path instead of sharing general git writing behavior.
* **Move screenshot suggestions into the writing phase**
  * Screenshot guidance now appears during writing instead of waiting for review.
* **Use anchored screenshot comments instead of file markers**
  * Screenshot suggestions now attach to exact passages through anchored comments instead of editing the document with markers.

#### 🐛 Bug Fixes

* **Fix SelectedCommentsProvider cleanup behavior**
  * Selected comment state handling now uses cleaner property assignment and simpler disabled reason logic in non editable states.
* **Strengthen conversation diff history tracking**
  * Conversation diff history now backfills missing entries, records patch level details and exact file versions, avoids duplicate backfills, and uses more consistent request handling.
* **Clarify cumulative diff and reasoning output**
  * Diff views now group patch history by file for a clearer final change summary, and patch application no longer adds separate reasoning comments that repeat the same context.
* **Stop same issue follow ups from editing an open pull request**
  * Doc Holiday now blocks same issue follow up requests from trying to edit a pull request after it is already open.
* **Route Bitbucket review replies to the right pull request**
  * Bitbucket pull request comment replies now stay attached to the existing documentation pull request instead of risking a duplicate one.
* **Use the right pull request type for GitHub comment origins**
  * GitHub pull request comments now record the correct origin type instead of falling back to a more generic issue type.
* **Hide reply input during comment edits**
  * Users no longer see reply and edit inputs at the same time on the same comment.
* **Keep bot comments from looking outdated too easily**
  * Automated comments no longer pick up outdated badges just because a file SHA changed.
* **Prevent bot comments from appearing in selectable comment actions**
  * File comment selection now ignores bot authored comments so only user comments appear in those actions.
* **Return comments from discussion only actions**
  * Discussion only flows now return the comments they create instead of hiding them from the result.
* **Fix comment input overflow on small diffs**
  * File comment inputs now stay within layout bounds even when a diff shows only a few lines.
* **Wrap long comment text more cleanly**
  * Long comment content now wraps without overflowing the interface.
* **Keep resizable sheets from scrolling the page behind them**
  * The background page no longer scrolls while the cursor is over a resizable sheet.
* **Fix file view overflow and diff header rendering**
  * Work History file views now fit content more cleanly and avoid awkward diff header rendering.
* **Scroll opened comment groups into view**
  * Expanded file comment threads now move into view automatically so they are easier to find.
* **Fix line range badges and controls**
  * Line range badges now avoid extra arrow clutter and related comment group code no longer interferes with focus behavior.
* **Fix comment form wiring**
  * Comment batch input now uses the correct form wiring instead of a broken import path.
* **Fix new comments on older file SHAs**
  * Users can now create comments against older file versions more reliably.
* **Fix GitHub install redirects**
  * GitHub App installation now returns users to the host captured during setup instead of the wrong host.
* **Stop retrying missing GitHub branch lookups**
  * The files tab now fails fast on missing GitHub refs instead of spinning through pointless retries.
* **Treat GitHub 500 errors as temporary**
  * Retry logic now recognizes GitHub 500 responses as transient failures.
* **Guard GitHub response handling better**
  * GitHub client checks now confirm responses exist before reading response properties.
* **Retry failed GitHub pull request patch calls**
  * GitHub pull request updates now retry temporary `502 Bad Gateway` failures.
* **Improve pull request review test stability**
  * Review flow validation now checks commit count growth more reliably.
* **Retry transient Bitbucket commit discovery failures**
  * Recently pushed Bitbucket branches now recover better from temporary `404` delays during commit discovery.
* **Retry Bitbucket fork creation under throttling**
  * Bitbucket end to end setup now handles rate limiting more gracefully when creating forks.
* **Clarify Bitbucket E2E setup requirements**
  * The setup guide now makes it clear that only the main Bitbucket token is required and that related variables are optional defaults.
* **Fix Slack installation edge cases**
  * Slack setup now handles missing OAuth URLs, installed channel pagination, team names, health checks, and redirect safety more cleanly.
* **Show translated global error messages correctly**
  * Global error pages now load translated strings correctly, including comment send failures.
* **Rename run logs cleanly in stored data**
  * Audit log data now handles nullable names and time normalization more accurately.
* **Fix previous page pagination logic**
  * Reverse paging now respects ascending and descending sort order correctly.
* **Reduce automation name collision mistakes**
  * Automation updates now catch real duplicate names without blocking a record from keeping its own name.
* **Keep uploaded file changes from stalling on pull request refresh**
  * User uploaded changes now finish faster because upload completion no longer waits on extra pull request state refresh work.
* **Hide Notify until work is ready**
  * Users no longer see the Notify action while a conversation is still running.
* **Tolerate duplicate session auth rows**
  * Session reuse now remains stable even when duplicate session authentication rows already exist.
* **Lock session token allocation to the signed in user**
  * Session token allocation now stays tied to the current authenticated user instead of risking cross user mix ups.
* **Avoid reacting to comments that do not ask for work**
  * Upstream comments that are not actually requesting Doc Holiday work now no longer trigger reactions or progress activity.
* **Prevent literal Markdown from leaking into summaries**
  * Generated merged summaries now avoid exposing raw Markdown formatting tokens.
* **Stop repeated deletion of already deleted organizations**
  * Organization deletion now ignores records that were already soft deleted.
* **Clear connection secrets on delete**
  * Deleted connections now remove their stored secrets instead of leaving secret data behind.
* **Keep all relevant files in annotator output**
  * Annotation now requires all relevant files before completion and uses deterministic source labels for more reliable reasoning output.
* **Stop annotator failure loops earlier**
  * Annotation recovery now caps repeated retry loops and can give up gracefully after repeated missing file failures.

### 2026-05-08

#### 🚀 New Features

* **Enable JIRA Ticket Search & Lookup**
  * Automations can now search JIRA tickets and open individual ticket details from connected JIRA sources.
* **Add Persistent User Sheet Sizing**
  * The hidden user editor now remembers its size so repeated access feels more consistent.
* **Add Connection Health Checks**
  * AWS, Zendesk, Notion, Linear, and documentation site connections can now report explicit health status through the same connection health experience.
* **Add Bitbucket Pull Request Interactions**
  * Doc Holiday can now create comments, update comments, and reply to `@doc.holiday` mentions on Bitbucket pull requests with progress updates.
* **Add Work History Links to Pull Requests**
  * Generated pull requests now link back to the originating Work History entry.

#### ✨ Enhancements

* **Improve Bitbucket Request Handling**
  * Bitbucket branch creation, lookup, and deletion now follow the same flow.  
* **Improve Work History Health Failure Feedback**
  * Failed connection and publication health tests now show the failure reason directly in dashboard toasts.
* **Relax Publication Save Rules**
  * Publications can now save even when no reaction option is selected.
* **Improve Full Branch Retrieval**
  * GitHub and GitLab connection setup now loads complete branch lists instead of partial listings.
* **Polish Publication Label Styling**
  * Additional Instructions labels now stand out more clearly in the dashboard.

#### 🐛 Bug Fixes

* **Show Failed Health Test Reasons**
  * Failed connection and publication health tests now show the reason directly in dashboard toast messages.
* **Handle Large GitHub Directories**
  * GitHub file access now works in directories with more than 1000 entries instead of returning false missing file results.
* **Reduce False Mention Triggers**
  * Mention detection now ignores later message references that previously triggered Doc Holiday by mistake.
* **Fix Zendesk Link Crashes**
  * Zendesk link checks now recover safely when a parsed link is missing and rebuild the link when needed.
* **Clarify Work History Error Messages**
  * Work History cleanup now reports pull request loading failures more accurately.
* **Block Duplicate Connection Setups**
  * Connection setup now blocks conflicting saved configurations before overlapping records are stored.
* **Restore Immediate Connection Removal**
  * Deleted connections now disappear from the dashboard immediately while related lists refresh in the background.

### 2026-05-01

#### 🚀 New Features

* **Introduced changelog configuration guidance**
  * Publications can now store changelog specific instructions so changelog updates can follow the right publication rules.
* **Launched richer Work History review**
  * Work History now offers a fullscreen side sheet, richer diff and preview modes, and persistent panel sizing.
* **Added publication and source search**
  * Publications, sources, and providers now support search.

#### ✨ Enhancements

* **Improved list preference memory**
  * Work History and publication lists now remember sorting and filtering preferences across sessions.
* **Restored Work History side sheet review**
  * Work History details now stay in a side sheet so teams can inspect changes without leaving the main view.
* **Sharpened Work History layout**
  * Work History now preserves the selected tab in fullscreen mode, uses the full available width, and adds more breathing room at the bottom of the panel.
* **Clarified instruction labels**
  * Publication setup now labels writing guidance and style guidance more clearly so teams can understand those inputs faster.
* **Refined empty repository guidance**
  * GitHub onboarding now shows a clear actionable error when a connected repository is empty.
* **Strengthened repository health reporting**
  * GitHub repository checks now report unexpected reference problems more accurately instead of showing a healthy result.
* **Improved pull request title suggestions**
  * Pull request title suggestions now use more context about what started the work.
* **Standardized connection behavior**
  * Connection behavior now stays more consistent across providers for connection checks and shared source handling.

#### 🐛 Bug Fixes

* **Prevented GitHub retry crashes**
  * GitHub retry handling now avoids a nil response crash path during pull request update retries.

### 2026-04-24

#### 🚀 New Features

* **Enable Zendesk source connections**
  * Teams can now connect Zendesk as a source and use it in generated work.
* **Provide access tokens for protected docs**
  * Teams can now connect private documentation sites through access tokens.

#### ✨ Enhancements

* **Clarify disabled messaging states**
  * Work History now shows a dedicated working placeholder when messages are temporarily unavailable.
* **Improve Work History file review**
  * Work History now shows cleaner file status presentation, steadier selectors, clearer links, and a smoother review layout.
* **Improve publication setup controls**
  * Publication setup now uses clearer input styling, searchable selectors, and cleaner form spacing.
* **Update GitHub installation setup**
  * Canceled GitHub App install requests now clear correctly instead of leaving setup stuck in a pending state.
* **Streamline publication editing**
  * Pre-set voice preferences no longer appear in publication configuration flows.
* **Open pull request links in a new tab**
  * Teams can now inspect pull requests without leaving the current review page.
* **Pull linked source material into automated runs**
  * Non-interactive automation runs can now include linked source material more reliably.
* **Sharpen dashboard table layout**
  * Shared tables now keep more stable column widths for clearer reading.
* **Ignore draft GitHub releases**
  * Draft GitHub releases no longer trigger documentation generation.
* **Proactive discovery for Azure & S3 sources**
  * Azure & S3 links are now discovered automatically instead of being user-supplied.

#### 🐛 Bug Fixes

* **Correct message warning scope**
  * Work History now shows unable to message warnings only when they truly apply to open pull requests.
* **Resolve text wrapping in run details**
  * Long content in Work History details now wraps cleanly instead of overflowing.
* **Correct API key setup**
  * New API keys now save with the correct authentication type during dashboard setup.
* **Prevent accidental file replacement**
  * Create file requests now stop before replacing an existing published file.
* **Fix hover sizing in file cards**
  * File cards now keep the correct height while hovering.
* **Stop selector scroll jumps**
  * Work History selectors and shared dropdowns now behave more reliably without unwanted scrolling.
* **Correct changelog write behavior**
  * Disabled changelog settings now prevent accidental changelog updates.

### 2026-04-17

#### 🚀 New Features

* **Improve Doc's Notes review tools**
  * Work History now supports searching, filtering, sorting, and easier note exports for Doc's Notes.

#### ✨ Enhancements

* **Make publication setup easier to search**
  * Publication setup now uses searchable selectors for sources, targets, and connection types, with easier selection of multiple source repositories.
* **Paginate dashboard lists**
  * Sources, Providers, and Publications now offer previous and next navigation for long lists.
* **Upgrade voice preference editing**
  * Writing preferences now use a richer editor with preview support for prompt customization.
* **Refine contribution rule handling**
  * Generated pull requests and commits now follow publication specific commit rules, signoff requirements, merge preferences, and pull request instructions more closely.
* **Polish GitHub install setup**
  * GitHub App setup now uses clearer wording, restored admin invite links where needed, and a more consistent pending approval badge.
* **Add changelog controls**
  * Publication setup now includes controls for enabling changelog writing alongside other writing features.
* **Improve Work History messaging**
  * Work History now uses clearer message wording, better disabled state explanations, cleaner markdown links, and less visual clipping in message cards.
* **Improve note wrapping**
  * Work History notes now wrap long text more cleanly with stronger hyphenation and overflow handling.

#### 🐛 Bug Fixes

* **Reduce publication form flashing**
  * Publication forms now keep loading states active while connection options continue loading, which makes editing feel more stable.
* **Correct approved install audit logs**
  * Administrator approved GitHub App installs now record clearer audit log entries with proper user attribution.

### 2026-04-10

#### 🚀 New Features

* **Show full file previews in Work History**
  * Work History now shows markdown and file contents instead of only a diff style preview, with clearer loading and error states.

#### ✨ Enhancements

* **Refine Work History tab styling**
  * Work History tabs now use a cleaner visual treatment without the extra background fill.
* **Display a skipped status icon**
  * Doc Holiday now shows skipped progress states with an icon style indicator instead of plain text.

#### 🐛 Bug Fixes

* **Keep generation running after rewritten Git history**
  * Documentation and release note runs now continue with reduced context instead of failing when repository history changes after a force push or rebase.

### 2026-04-03

#### 🚀 New Features

* **Expanded conversation turns and retry controls**
  * Teams can now follow each exchange across work runs and retry work with fuller context in Work History.
* **Refined pull request title setup before creation**
  * Teams can now prepare custom pull request titles in advance, apply title guidance more consistently, and keep chosen titles attached to each work item.
* **Added rich diff views in Work History**
  * Work History now shows clearer file comparisons so teams can review changes more easily from the files page.

#### ✨ Enhancements

* **Enhanced commit summaries for larger review windows**
  * Commit summaries now read more clearly for split or lengthy changes and cover long review windows more completely.
* **Clarified GitHub install request guidance**
  * GitHub install request screens now use clearer wording and remove the cancel authorization link to reduce setup confusion.
* **Improved requested time window calculations**
  * Commit and release windows now match the requested time period more reliably.

#### 🐛 Bug Fixes

* **Recovered from file content lookup failures**
  * AI work now recovers gracefully when target file content cannot be read during file listing instead of ending the run.
* **Restored fallback categories for uncategorized notes**
  * Release note generation now assigns a default category when no match appears, which prevents empty grouping results.
* **Corrected pull request source links in GitHub views**
  * GitHub pull request references now point back to the correct review page.

### 2026-03-20

#### 🚀 New Features

* **Azure Blob Storage connection**
  * Added an Azure Blob Storage connection type.
* **AWS S3 connection**
  * Added an AWS S3 connection type.

#### 🐛 Bug Fixes

* **GitLab provider type validation**
  * Fixed GitLab provider connection handling to return errors for unsupported connection types instead of panicking.
* **GitHub API retries**
  * Fixed transient GitHub API failures by retrying provider operations.

### 2026-03-06

#### 🚀 New Features

* **Add File dialog with path suggestions**
  * Added an Add File dialog that uploads new files to a work item with repository path suggestions.

#### ✨ Enhancements

* **Conversation-based work status model**
  * Updated work status values to `ConversationStatus` (`open`, `staged`, `running`, `closed`, `merged`) (breaking change).
* **Augmented external link parsing across providers**
  * Added support for more types of link parsing and reading across providers, such as JIRA (e.g. "PROJ-123"), GitLab, and Notion URLs.

#### 🐛 Bug Fixes

* **Work-state cleanup normalization**
  * Fixed work-state cleanup to recompute status and reduce stale summaries on failures.

### 2026-02-26

#### 🚀 New Features

* **Publishing-system selector in onboarding**
  * Introduced an optional publishing-system selector to onboarding and connection setup.
* **Expanded issue trigger reactions**
  * Enabled issue and issue-comment trigger reactions for issue-based automation events.
* **Enhances requests to move content**
  * Supports reorganizing multiple sections within the same file, and recognizing sections by descriptions instead of line numbers.

#### ✨ Enhancements

* **Repository selection bulk actions**
  * Introduced select-all and clear-all controls for visible repositories during onboarding.
* **Theme-friendly success indicator**
  * Updated the success checkmark to use an inline SVG and standardized success messaging.
* **Conditional diff loading**
  * Updated work state details to load diffs only when relevant.
* **Provider-connection filtering in publication inputs**
  * Updated publication inputs to exclude GitHub and GitLab provider connections.
* **Connection sync action removal**
  * Removed the dashboard connection sync action (breaking change).
* **Legacy CRM integrations removal**
  * Removed Zendesk and Salesforce integrations and legacy customer and issue models (breaking change).
* **Create-file overwrite protection**
  * Updated create-file requests to fail when the destination exists to prevent accidental overwrites (breaking change).

#### 🐛 Bug Fixes

* **Branch label loading state**
  * Fixed branch labels to avoid showing `...` when a branch is already selected.
* **Claim timestamp population**
  * Fixed claim creation to populate `updated_at` at insert time.

### 2026-02-20

#### 🚀 New Features

* **Reset-file branch-only cases**
  * Fixed reset-file behavior for branch-only file existence cases.

#### ✨ Enhancements

* **Onboarding experience updates**
  * Updated UI behavior and copy to improve onboarding clarity and feedback during key workflows.
* **Request-type guidance and routing**
  * Updated request-type guidance and routing to reduce ambiguity between reset and edit operations.
* **Toast duration updates**
  * Dropped default toast notification times so they don't need to be manually closed.
* **Close-Issue removal**
  * Removed active execution support for the deprecated `close-issue` request type (breaking change).
* **Job creation request deprecation**
  * Deprecated the job creation request type where applicable to guide migration to newer flows.
* **Dependency security updates**
  * Updated third-party dependencies to address upstream security advisories.

#### 🐛 Bug Fixes

* **Release-notes pull request draft status**
  * Updated release-notes pull request draft status to match release stages more consistently.
* **Work-state pagination rename**
  * Renamed work state pagination from `token` to `next` (breaking change).
* **Pull request commit counting**
  * Fixed pull-request commit counting when upstream comparisons return zero commits but local pending commits exist.
* **Work-state output links**
  * Fixed work-state update behavior so output links are not lost during updates.
* **Publication dialog submission**
  * Fixed publication dialog submission behavior to prevent accidental form submits and invalid saves.

### 2026-02-13

#### 🚀 New Features

* **Demo flow v2**
  * Added a v2 documentation and release-notes demo mode driven by embedded demo assets and demo context metadata.

#### ✨ Enhancements

* **Connection health checks**
  * Updated GitHub and GitLab health checks to treat transient upstream 5xx errors as non-fatal.
* **Onboarding repository selection**
  * Updated onboarding and connection setup to make repository and branch selection clearer and more interactive.
* **Work history pagination**
  * Updated work history browsing to use paginated work-state listing for more consistent results at scale.

#### 🐛 Bug Fixes

* **Files tab without branch diffs**
  * Fixed the Work History Files tab to return empty diffs for branchless work states and show clearer error messages.
* **GitLab project listing errors**
  * Fixed GitLab project listing to provide clearer errors for invalid tokens and missing project lists.

### 2026-02-06

#### 🚀 New Features

* **Work item history file uploads**
  * Added file upload actions for individual work item history entries in the Files tab.
* **Antora publishing-system detection**
  * Added publishing-system recognition for Antora projects using `antora.yml` or `antora.yaml`.

#### ✨ Enhancements

* **Progress tracking across complex runs**
  * Updated step progress tracking and pull request association for more accurate reporting across complex runs.
* **Progress reporting for non-interactive runs**
  * Updated non-interactive automation runs to provide more complete progress reporting from start to finish.
* **Audit log navigation and layout**
  * Updated Activity Log labeling to Audit Log and refreshed the UI with a flat event table and a right-hand detail sheet.
* **Publication form validation feedback**
  * Updated publication create and edit forms to surface aggregated validation errors.
* **Faster work state UI hydration**
  * Updated grouped work history responses to pre-populate per work state cache entries for faster UI hydration.
* **Organization and connection lifecycle operations**
  * Updated organization upsert behavior and connection deletion workflows for clearer audit logging.
* **Work history UI action guarding**
  * Updated work history controls to disable messaging and file uploads while a pull request or merge request is pending.
* **Pagination cursor responses**
  * Updated list endpoints to return `previous` and `next` cursors and migrated pagination state to URL-based `nextToken` handling (breaking change).
* **Work history branch fields removed**
  * Removed `branch` from work history APIs (breaking change).
* **Run log model simplification**
  * Removed legacy run log fields and grouped hooks, and updated clients to use the single run log fetch API (breaking change).

#### 🐛 Bug Fixes

* **Work history timestamps**
  * Fixed work history label localization and updated created-time rendering to a formatted absolute `Started` timestamp.
* **Request summary publication names**
  * Fixed request summaries to use the actual publication name instead of repeated user-provided names.
* **Deleted publication label spacing**
  * Fixed deleted-publication labels to render the `(deleted publication)` suffix with correct spacing.
* **GitHub and GitLab path parsing**
  * Fixed GitHub file path parsing for edit URLs and updated GitLab merge request commit.

### 2026-01-30

#### 🚀 New Features

* **Work requests and jobs**
  * Introduced dashboard support for creating work requests and tracking them as jobs.
* **Test pull request or merge request onboarding**
  * Added onboarding guidance for opening a test pull request or merge request.
* **Resizable work history sheet**
  * Introduced a resizable sheet with tabs for file changes, downloads, and team messages per work item.
* **Work state file uploads**
  * Added support for uploading files from a work state to the publication repository.
* **Expanded publishing-system detection**
  * Expanded publishing-system detection to recognize additional documentation toolchains automatically.

#### ✨ Enhancements

* **Work history and jobs page performance**
  * Improved performance for work history and job-related pages while data is still being created or updated.
* **Progress reporting and run history logs**
  * Improved progress reporting and run history visibility across documentation and release-notes workflows.
* **Style guidance defaults**
  * Updated style guidance defaults to improve consistency in generated documentation and release notes.

#### 🐛 Bug Fixes

* **File path parsing and lookup**
  * Fixed file path handling for partial paths and platform-specific URLs to improve lookup reliability.
* **Work history and work state edge cases**
  * Resolved edge-case behavior in work history and work state APIs and tests.

#### 💼 Known Issues

* **Feature flag visibility**
  * Some job, work state, and messaging features can appear in the UI before they are enabled for all organizations.

### 2026-01-23

#### 🚀 New Features

* **Publication onboarding**
  * Introduced a multi-step setup flow for sources, triggers, voice preferences, and completion screens.

#### ✨ Enhancements

* **Work history grouping**
  * Improved status rollups for more reliable progress and timing information in run histories.
* **Publishing-system detection**
  * Updated documentation toolchain recognition.
* **Writing preferences**
  * Added per-document-type style guide settings and voice preferences.

#### 🐛 Bug Fixes

* **Run log tracing**
  * Corrected run logging so correlation identifiers remain consistent across related executions.

### 2026-01-15

#### 🚀 New Features

* **Onboarding v2**
  * Added a new step-by-step onboarding flow
* **Provider setup pages in onboarding**
  * Added provider-specific onboarding pages for GitHub and GitLab

#### ✨ Enhancements

* **Faster release notes generation**
  * Release notes generation now runs faster when previous daily summaries are already available
* **Connection setup provider switching**
  * Connection setup now makes it easier to switch between GitHub and GitLab connection options while entering details
* **Dashboard framework updates**
  * Updated the Doc Holiday dashboard to newer framework and library versions
* **Calendar control updates**
  * Updated the calendar control for more consistent navigation and date selection across the app
* **Sync requests with configurable timeouts**
  * Connection sync requests can optionally wait for completion with a caller-chosen timeout
* **Improved GitLab file link support**
  * GitLab file links can now be read as source material more reliably

### 2026-01-02

#### 🚀 New Features

* **Work History dashboard**
  * Work history dashboard now available for reviewing Doc Holiday's past work in a dedicated area in the dashboard
* **GitHub personal access token connections**
  * GitHub repositories can now be connected using a personal access token
* **GitLab providers and project connections**
  * GitLab now supports setting up as a reusable provider and attaching individual GitLab projects as connections

#### ✨ Enhancements

* **Publication deletion from edit page**
  * Publications can now be deleted directly from the update page
* **Source links in generated pull requests**
  * Generated pull requests now include clear links to their origin
* **Clearer run summaries in work history**
  * Work history dashboard now offers improved run summaries displaying what happened, triggers, and run durations
* **Refined work history layout**
  * Work history dashboard layout refined for more intuitive navigation, grouped runs, and clearer labels
* **GitLab project sync behavior**
  * GitLab project connections now maintain sync behavior consistent with other code hosts to ensure fresh changes
* **GitLab project webhook reliability**
  * Webhook reliability for GitLab project connections improved, especially when using a separate GitLab provider connection
* **GitLab setup documentation link**
  * Direct link to GitLab connection setup instructions now available for quick access to relevant documentation
* **Combined provider list view**
  * Providers page now lists GitHub and GitLab provider connections together for easier management
* **GitLab document links from configuration files**
  * GitLab-based document connections now incorporate web links from project configuration files to improve content discovery
* **GitHub access token targets in publications**
  * Publications setup now enables selection of GitHub access token connections as valid publishing destinations
* **Clarified connection setup instructions**
  * Setup instructions for GitHub and GitLab connections clarified for better understanding of repository and project linking

#### 🐛 Bug Fixes

* **Edit request robustness**
  * Edit requests now function more reliably when details are inconsistently formatted or messy
* **Login failure handling**
  * Login page now provides a clear error screen on underlying failures for better feedback
* **Connection status updates after errors**
  * Sync and health check statuses for connections now update promptly following errors, preventing outdated information
* **Provider list refresh after deletion**
  * Providers list in the app is refreshed upon login after a deletion to accurately reflect current connections
* **GitHub branches with slashes in listings**
  * Branches containing slashes are now included in GitHub branch listings, ensuring all available branches are selectable

### 2025-12-19

#### 🚀 New Features

* **Delegated install via invite link**
  * Developed a new flow wherein any user can invite an administrator to complete GitHub App installation.

#### ✨ Enhancements

* **Dedicated error page for GitHub App installation**
  * Added a standalone error interface in doc.holiday to explain GitHub App setup problems.
* **App installation confirmation view**
  * Introduced a confirmation screen that appears following successful (app or GitHub App) setups.
* **Step-by-step GitHub App install guidance in Connections**
  * Added guided walkthroughs to the Doc Holiday connection interface for GitHub App setup.
* **Streamlined onboarding for GitHub Apps**
  * Created enhanced public install and post-install pages for a smoother, simplified setup.
* **JIRA connectivity to individual projects**
  * Built in configuration options and dashboard management for adding JIRA projects as connections.
* **Clearer activity and run log summaries**
  * Enhanced labeling and distinction of failures, skips, and abstentions in all activity and run logs.
* **Refined user menus and button designs on dashboard**
  * Improved visual polish and usability of navigation and interactive elements.
* **Consistent dashboard look and feel**
  * Polished visual hierarchy and alignment across dashboard user menus and button layouts.
* **Sunset legacy org settings location**
  * Deprecated old organization configuration page and now redirect to the modern settings area.
* **Next.js library update**
  * Bumped Next.js to version 15.5.8 throughout app and shared packages.
* **Enhanced sync logging for connections**
  * Added last sync timestamp and sync count fields to every connection.

#### 🐛 Bug Fixes

* **Error page on login failures**
  * Improved authentication to redirect users to an error display on unexpected login issues.
* **Consistent run log filtering resets**
  * Changing the run log type always switches to the first page for clarity.

### 2025-12-12

#### 🚀 New Features

* **Jira project connections**
  * Added support for connecting Jira projects as sources, enabling Jira issues to be synced into Doc Holiday.

#### ✨ Enhancements

* **Dashboard and navigation polish**
  * Polished the Doc Holiday dashboard, navigation, onboarding, and settings screens for a cleaner, more consistent experience.
* **Form controls and status indicators**
  * Refined checkboxes, radio buttons, health badges, alerts, tabs, and cards across onboarding, publications, connections, and documentation views.
* **Settings layout updates**
  * Improved the Settings area so profile settings are now located under Settings → Profile with tabbed navigation.
* **Publication health warnings**
  * Updated publication health indicators so automations can show an “incomplete” warning state.
* **Publication update feedback**
  * Improved the Update Publication dialog with a clear loading state while changes are being saved.
* **Connections and Providers UI**
  * Refined the Connections and Providers pages, including GitHub and GitLab connection forms.
* **Run log wording**
  * Updated run log wording so completed work now uses a friendlier “wrote” label.
* **Git-based sync resilience**
  * Improved GitHub and GitLab sync behavior so hiccups while scanning individual claims are logged without failing the entire sync job.
* **Next.js platform upgrade**
  * Upgraded the Doc Holiday dashboard to a newer, security-patched Next.js version.
* **GitLab project selection UX**
  * Enhanced GitLab connections so an access token can be pasted and a selection can be made from a searchable list of available projects.
* **Documentation link routing**
  * Improved link reading so documentation links are matched more accurately to the right configured connection.
* **Warning card style**
  * Added a dedicated “warning” visual style for shared cards.
* **Jira health checks**
  * Added health checks for Jira project connections.
* **Jira webhook error reporting**
  * Improved Jira connection webhook error handling so responses from Jira are surfaced more clearly.

#### 🐛 Bug Fixes

* **UI card rounding**
  * Fixed visual rounding quirks in JavaScript UI cards and form components.
* **Git-based connection health checks**
  * Improved GitHub and GitLab connection setup so projects and repositories are listed more reliably.
* **Claim-level sync failures**
  * Updated Git-based connection syncing so errors while syncing individual claims no longer cause the entire sync job to be marked as failed.
* **GitLab form alignment**
  * Fixed alignment of labels in the GitLab connection form.

### 2025-12-05

#### ✨ Enhancements

* **GitHub App connection renaming**
  * Allowed renaming of existing GitHub App connections from the dashboard.
* **Git-based content processing reliability**
  * Improved Git-based content processing reliability for GitHub and GitLab sources.
* **AI inference robustness**
  * Updated the AI inference subsystem that handles OpenAI server errors for greater robustness.
* **Internal storage subsystem updates**
  * Updated internal storage subsystems to support future knowledge base capabilities.

#### 🐛 Bug Fixes

* **Next.js security updates**
  * Updated web application dependencies with the latest Next.js security fixes.

### 2025-11-21

#### 🚀 New Features

* **Empty states across the dashboard**
  * Added helpful empty states to Connections, Providers, Publications, and API Keys pages to guide setup and next steps

#### ✨ Enhancements

* **Cleaner Activity Log**
  * Removed connection sync entries to reduce noise and highlight user-driven events
* **Logs type selector simplification**
  * Removed the "General documentation updates" option from the logs type selector
* **Logo update**
  * Updated logo assets to remove the trademark symbol
* **UI sizing adjustments**
  * Refined layout and sizing for improved visual consistency

#### 🐛 Bug Fixes

* **Release notes PR titles**
  * Set the release notes PR's title without altering the original PR title
* **PR commit count**
  * Corrected the commit count shown in generated PR bodies
* **Activity Log stability**
  * Fixed issues impacting Activity Log accuracy and updates
* **Revert request validation**
  * Enforced non‑negative recentCommitCount values in revert requests to prevent errors

### 2025-11-14

#### 🚀 New Features

* **Delete automations from Publications list**
  * Allowed automations to be deleted directly from the Publications list page for faster cleanup

#### ✨ Enhancements

* **Line‑scoped review comments**
  * Scoped GitHub review comments made on a single line to only that line to to enable support for single-line manipulations in GitHub
* **Merge PR pre‑check**
  * Added early validation requiring a PR as the starting point before merging
* **Differentiated PR titles**
  * Differentiated generated pull request titles to improve clarity
* **Include style guide in success messages**
  * Included the selected style guide in success messages for quick reference
* **Sensitive data redaction in logs**
  * Removed potentially sensitive content from logs to improve security

#### 🐛 Bug Fixes

* **Navbar icon alignment**
  * Fixed icon alignment issues in the top and left navigation bars
* **Delete orphaned documents on connection removal**
  * Deleted documents when their connection was removed to prevent orphaned content
* **Button spacing**
  * Enforced spacing between Skip and Next buttons for consistent layout
* **Canvas zoom prevention**
  * Prevented zooming on the publications canvas to reduce accidental zoom gestures

### 2025-11-07

#### 🚀 New Features

* **API Keys management page**
  * Added a dedicated Settings > API Keys page to create, name, and manage keys with expirations
* **Added API Support**
  * Released customer-facing API to automate Doc Holiday integration into release pipelines
* **Linear Issue URL Support**
  * Allow Linear issue URLs to be included as context in API calls for documentation and release notes generation
* **Edit from prompt: “this file” / “these files”**
  * Enabled targeting the current file or selected files when editing from a prompt for more precise changes

#### ✨ Enhancements

* **Streamlined Activity Log Interface**
  * Frontloaded changes toward a simplified logging experience for clearer diagnostics
* **Explicit addressing requirement**
  * Required requests to explicitly mention @doc.holiday to trigger actions, reducing accidental runs
* **Progress tracker resilience**
  * Continued subsequent steps even when a prior one failed and avoided reporting success if any step failed
* **PR summary ordering**
  * Improved the ordering of URLs so generated summaries match the progress tracker
* **Date/time picker UX**
  * Centered controls and ensured the calendar opens below fields; API key expirations now use a 24‑hour time picker
* **API Keys under Settings**
  * Moved the API Keys page beneath Settings for clearer navigation
* **API key creator visibility**
  * Displayed the user name of the API key’s creator on the keys list
* **API key card styling**
  * Matched design borders and formatted keys as a vertical list with a vertical ellipsis actions menu
* **Onboarding guard**
  * Prevented navigation to Publications during onboarding until at least one connection exists
* **Publication reference fallback**
  * Logged ambiguities when a request specifies an unclear publication instead of failing

#### 🐛 Bug Fixes

* **Pagination page skipping**
  * Fixed a pagination bug that could skip pages when navigating lists in activity log
* **Deleted API key handling**
  * Returned a clear unauthenticated error when a deleted API key is used
* **Settings tab styling**
  * Corrected API Keys page styling to match the Settings tab appearance

### 2025-10-31

#### 🚀 New Features

* **Tag-based commit ranges**
  * Added support to select commits between tags and since a tag across GitHub and GitLab, making it easier to generate release notes by release
* **Arbitrary PR/MR commit selection**
  * Enabled retrieving commits from specified pull requests or merge requests to target updates precisely

#### ✨ Enhancements

* **Activity Log pagination**
  * Omitted the Next button on the final page to reduce confusion
* **Providers page cleanup**
  * Removed the Add connection button from the providers page
* **Publication source checkboxes**
  * Increased checkbox size for easier selection
* **Request understanding**
  * Stopped auto-disambiguating generic “documentation” requests into release notes for more accurate routing

#### 🐛 Bug Fixes

* **Tag-range comparison**
  * Corrected ref comparison values for tag ranges to return the expected commit set
* **Connection form submission**
  * Waited for connection creation to finish before navigating to prevent partial setup
* **GitLab onboarding redirect**
  * Prevented redirect to onboarding when a GitLab connection and publication already existed
* **Tab route matching**
  * Fixed route matching so the correct tab stayed active
* **Providers page wobble**
  * Smoothed animation to eliminate a visual wobble
* **Publication errors display**
  * Hid overflow for long error messages on the publications page to improve readability

### 2025-10-24

#### 🚀 New Features

* **API Key Expiration**
  * Added support for listing and creating API keys with expiry dates, allowing users to manage key lifecycles more effectively
* **Prompt-based File Editing**
  * Added a feature to edit files interactively using prompts along with commit history, enabling guided file modifications
* **Named Publication and Automation Selection**
  * Support for specifying publications or automations by name in requests, including prefix, suffix, and “named like” patterns

#### 🐛 Bug Fixes

* **Release Event Processing**
  * Fixed handling of GitHub and GitLab release webhook events by removing deprecated parameters and ensuring release events are processed correctly

### 2025-10-17

#### 🚀 New Features

* **Release Note “This PR” Scope**
  * Added support for the “this PR” scope in release note generation, allowing release notes to be generated for the current pull request
* **Automated Documentation Updates & Creation**
  * Introduced new methods for updating existing documentation and generating new docs based on commits, comments, and style guides
* **Linear Issue & Label Management**
  * Added API support for creating issues, adding comments, and fetching labels in Linear integrations

#### ✨ Enhancements

* **Optimized Context Overflow Handling**
  * Improved OpenAI model context overflow logic with callbacks to gracefully trim and manage large contexts

#### 🐛 Bug Fixes

* **GitHub PR Reload Branch References**
  * Fixed branch reference handling when reloading GitHub pull requests to maintain correct refs
* **Repository Sorting Robustness**
  * Ensured repository lists sort correctly when `fullName` is `null` or undefined
* **GitLab Connection Type Field**
  * Fixed handling of the `type` field in GitLab connections for accurate configuration
* **GraphQL Issue Query Syntax**
  * Corrected a GraphQL syntax error in the `GetIssue` function for accurate issue data retrieval
* **Error Handling in mustGet**
  * Updated the `mustGet` function to catch fetch errors and return `undefined` instead of throwing
* **Hesitation Error Messaging**
  * Improved progress tracker to properly handle and display hesitation errors with clear user messages
* **GetIssue Fetch Robustness**
  * Updated error handling in data fetch utilities to prevent unhandled exceptions

### 2025-10-10

#### 🚀 New Features

* **Run Logging Status**
  * Added `status` field to run logs (`success`, `running`, `error`), updated database schema, data models, and API to create, retrieve, and update run logs; now logs automation and connection events with status updates
* **GitLab Issue & MR Closing**
  * Added support for closing GitLab issues and merge requests via API; integrated `Close` operations into workflow handlers and client interfaces for programmatic issue and MR management

#### ✨ Enhancements

* **Authentication for Documentation Crawling**
  * Added UI fields and backend support for basic and bearer authentication when crawling protected documentation sources.

#### 🐛 Bug Fixes

* **Documentation Sync Crash Prevention**
  * Added null/empty target attribute checks in the documentation sync process to prevent potential panics.

***

### 2025-10-03

#### 🚀 New Features

* **Linear Connection Type**
  * Added a new Linear connection option in the UI with API key input fields for seamless integration.
* **Manage Linear Issues & Comments**
  * Added ability to create, retrieve, update, and react to Linear issues and comments via API and Webhooks, enabling full Linear issue tracking within Doc Holiday.
* **’Eyes’ Reaction for Linear Comments**
  * Introduced support for adding and removing “eyes” reactions on Linear issue comments.
* **Confluence Integration**
  * Added support for Confluence connections, including content retrieval, updates, deletions, and management of attachments, labels, comments, watchers, and revision history.
* **Source Document Requests**
  * Enabled support for source document requests in automated release note and documentation workflows, generating PRs based on user comments and commit data.

#### ✨ Enhancements

* **Authentication for Documentation Crawling**
  * Added UI fields and backend support for basic and bearer authentication when crawling protected documentation sources.
* **Cross-Platform Repository Links**
  * Improved link extraction to list file links correctly for both GitHub and GitLab repositories.

#### 🐛 Bug Fixes

* **Documentation Sync Crash Prevention**
  * Added null/empty target attribute checks in the documentation sync process to prevent potential panics.
* **GitLab File Path Parsing Fix**
  * Added missing validation for GitLab file paths and improved logging to prevent sync errors.

***

### 2025-09-26

#### 🚀 New Features

* **GitHub Workflow Run Automations**
  * Introduced support for `workflow_run` events to trigger automations (assessments, PRs, release notes).

#### ✨ Enhancements

* **Cross-Platform Comment & Merge Automations**
  * Enabled GitHub issue comments to produce GitLab merge requests and added support for managing GitLab merge-request comments (add, edit, delete, reactions).

#### 🐛 Bug Fixes

* **Document Table UI**
  * Corrected visual layout issues in document tables across the documentation and activity-log pages by improving row-border rendering.
* **Reaction Placement**
  * Fixed reactions to target the last comment event on GitHub issues rather than the entire issue.
* **Automation Reaction Logic**
  * Corrected issue-handling logic to trigger automations accurately based on source vs. documentation repository roles.

***

### 2025-09-19

#### 🚀 New Features

* **Experimental Documentation Generation**
  * Trigger documentation updates or create experimental documentation pull requests directly through issue comments labeled `LabelDocHolidayExperimental` or release events.
* **File Bookmarking**
  * Save and revisit important source and target repository files with bookmarking functionality.

#### ✨ Enhancements

* **Cross-Platform Automation Enhancements**
  * Create GitLab merge requests from GitHub issues and GitLab issues from GitHub, including GitLab→GitLab pull requests and improved parity across platforms.
  * Retrieve commit ranges and compare tags to commits in GitLab.
* **Dashboard UI Improvements**
  * Added a **Danger Zone** section in the dashboard for deleting publications and connections with clear warnings.
  * Enhanced interactivity and error handling in the publications dashboard when data fetches fail, with integrated error messages and action options.
* **New UI Components**
  * Introduced a **destructive** variant for the Card component to emphasize critical actions.
  * Added support for **Notion** connections with UI fields for naming and integration keys.
  * Added a **Command** component (command palette dialog) for quick access to commands and actions.
  * Renamed **Run Log** to **Activity Log**, with detailed log views, expandable entries, and improved styling.

#### 🐛 Bug Fixes

* **Pull Request Logic**
  * Prevented null pointer exceptions in pull request handling by safely accessing file path and content.
* **Navigation Tabs**
  * Fixed tab highlighting in nested routes to ensure the correct active state based on URL.
* **Duplicate Issue Comments**
  * Prevented duplicate automated comments on new issues when source and documentation repositories are the same.
* **Publication Connections**
  * Automatically removed invalid connections during publication updates to prevent errors.

***

### 2025-09-05

#### 🚀 New Features

* **Publications Form & Onboarding Enhancements**
  * Implemented a new Publications form with UI components for creating and managing publications and connections.
* **Commit Reversion Support**
  * Added support for reverting individual commits within pull requests, including tools to fetch PR contents and create revert commits.

#### 🐛 Bug Fixes

* **Invalid Episode ID Warning Cleanup**
  * Updated system and user templates to return an empty JSON object, resolving persistent warnings from invalid episode ID prompts.

***

### 2025-08-29

#### 🚀 New Features

* **Release-Based Time Ranges**
  * Added support for `release` range types and “since the last release” in time calculations for commits and documentation generation.
* **Google Drive Connections UI**
  * Added buttons and dialog components in the Doc Holiday UI for provisioning Documentation and Google Drive connections.
* **Documentation Site Connections Management**
  * Introduced new dashboard UI components for creating and managing documentation site connections; connection types now include “documentation.”

#### ✨ Enhancements

* **Enhanced Encoding Support**
  * Updated the `tiktoken` dependency to v0.1.7 and added an `o200k_base` encoding to support larger token limits.

#### 🐛 Bug Fixes

* **Nullable Array Fields**
  * Fixed validation and rendering for nullable array types in the frontend schema.
* **Merge Fail Safeguard**
  * Prevented accidental file loss on document merge failure by returning early to avoid unintended deletions.
* **Skip Non-UTF8 Files**
  * Now skips non-UTF8 encoded text files during synchronization to prevent invalid content storage.

***

### 2025-08-27

#### 🚀 New Features

* **Fallback Operations Contextual Awareness**
  * Fallback documentation and release note generation now accesses prior assessment commit history and commit messages for improved context awareness. This results in more accurate, contextually-informed release notes and documentation, especially when user requests refer to earlier work or source PRs.

#### 🐛 Bug Fixes

* **Skip non-UTF8 strings when syncing GitHub files**
  * Added logic in `sfs/internal/logic` to ignore files containing invalid UTF-8 content, preventing corruption of the database.

***

### 2025-08-26

#### 🚀 New Features

* **Documentation Connection Type**
  * Introduced a new documentation connection type in the UI with components for creating and listing documentation site connections.
* **GPT-4o model encoding support**
  * Upgraded the tiktoken dependency to v0.1.7 and introduced the `o200k_base` encoding to enable GPT-4o tokenization.
* **Plumb previous assessment commits into fallback assessor**
  * Enables retrieval of previous assessment commit messages and diffs in fallback GitHub operations for improved context in subsequent actions.

#### ✨ Enhancements

* **Prevent stale documentation in PR edits**
  * Documentation edits now fetch documents based on the PR’s current head commit. If the SHA matches the last assessment, it falls back to using the last assessment’s documents; otherwise, it retrieves fresh documents from GitHub. This ensures edits no longer operate on stale PR documents.
* **Include connection ID in document metadata**
  * Each document now includes its originating connection ID in metadata for improved traceability.
* **Improved Document Merging Prompt**
  * Introduced a new `combine_documents` prompt version that preserves original text, prevents rephrasing, and precisely handles duplicates and conflicts. Updated configuration to replace older templates and streamlined the input schema.

***

### 2025-08-25

#### 🚀 New Features

* **GitHub Repository Selector**
  * Connection creation forms now include a repository dropdown in both onboarding and modal flows.

#### 🐛 Bug Fixes

* **Connection Cache Consistency**
  * Fixed caching logic in `useConnections` hooks to ensure consistency when creating or updating connections by type.
* **Fixed documentation links**
  * Updated the help route and dashboard links to point directly to official documentation.

***

### 2025-08-22

#### ✨ Enhancements

* **'Connections'**
  * Renamed 'Sources' to 'Connections'

#### 🐛 Bug Fixes

* **Document Editor Logging**
  * Moved the “no subject” safeguard log message in the document editor one line outward to ensure it appears when no subjects are provided.

***

### 2025-08-21

#### 🚀 New Features

* **Sources Page Enhancements**
  * Added a **Delete** button and dropdown menu on the Sources page, enabling direct testing, syncing, or deletion of connections.
  * Connections now automatically synchronize immediately upon creation and support partial sync when edited.
  * Improved the connection creation dialog for conditional rendering and faster form initialization.

#### ✨ Enhancements

* **Reduce verbosity of reaction-related logging**
  * Simplified internal logs and progress tracking for reactions in source repositories during pull request handling.

#### 🐛 Bug Fixes

* **Onboarding Sources Route**
  * Corrected the label and URL in the onboarding flow to point to the accurate Sources route instead of Connections.

***

### 2025-08-01

#### 🚀 New Features

* **Source & Publication Health Monitoring**
  * Added a health status badge into the UI on source and publication cards, with an error hint and a manual “Test” action when an automation is unhealthy.
* **Sources Page Enhancements**
  * Added a **Delete** button and dropdown menu on the Sources page, enabling direct testing, syncing, or deletion of connections.
  * Connections now automatically synchronize immediately upon creation and support partial sync when edited.
  * Improved the connection creation dialog for conditional rendering and faster form initialization.

#### 🐛 Bug Fixes

* **GCP Connection Authentication**
  * Fixed the handling of the GCP service account JSON when establishing connections, ensuring credentials are correctly populated for the GCP client.

***

