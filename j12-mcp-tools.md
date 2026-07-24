# MCP Tools

The Doc Holiday plugin registers a set of MCP tools your coding agent uses to drive the documentation service — listing your publications, submitting work, and tracking each request. Every tool name is prefixed `doc_holiday_`. The tools require an API key configured for your organization; the first call prompts a one-time sign-in.

The tools fall into two groups: **request** tools that submit new work, and **read** tools that report on your publications and work. Listing tools use passthrough pagination — pass `pageSize` and `next`, and read `nextPageToken` from the result.

## Request tools

| Tool | Purpose | Arguments |
| --- | --- | --- |
| `doc_holiday_request_documentation` | Submit a documentation prompt for a publication and get the handle back immediately. Omit `conversationId` to start a new conversation; pass it to add the prompt to an existing one. | `publicationId` (required), `prompt` (required), `conversationId`, `labels[]` |
| `doc_holiday_request_work` | Post a work request to an existing conversation — adds a work-requested comment with your message and returns it as a handle to track. | `conversationId` (required), `body` (required), `labels[]` |

## Read tools

| Tool | Purpose | Arguments |
| --- | --- | --- |
| `doc_holiday_list_publications` | List the publications for your organization. | `pageSize`, `next` |
| `doc_holiday_get_publication` | Return one publication by id. | `id` (required) |
| `doc_holiday_list_conversations` | List conversations, optionally filtered. | `publicationId`, `status`, `jobId`, `pageSize`, `next` |
| `doc_holiday_list_conversation_turns` | List the turns of conversations, optionally filtered. | `conversationId`, `status`, `pageSize`, `next` |
| `doc_holiday_get_conversation_turn` | Return one turn — its plan, request, status, and summary. | `turnId` (required) |
| `doc_holiday_get_conversation_diffs` | Return the file diffs produced in a conversation. | `conversationId` (required) |
| `doc_holiday_list_conversation_comments` | List comments on conversations. | `conversationId`, `workRequested`, `pageSize`, `next` |

## Related

- [Install the Doc Holiday plugin](./g5-install-plugin.md) — how these tools get registered.
- [Plan and generate docs with skills](./g6-plan-generate-with-skills.md) — the skills that produce the prompts these tools submit.
- [Work History API](./j4-api-work-history.md) — the same operations over plain REST.
