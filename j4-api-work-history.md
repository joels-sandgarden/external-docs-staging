# Work History API

This page covers direct integration with Doc Holiday's API.
The API resource uses `conversations`, and the app calls it Work History.
This page documents only the public `/api/v1/conversations*`, `/api/v1/conversation_comments*`, and `/api/v1/conversation_turns/{id}/retry` routes.

## `conversations`

### `GET /api/v1/conversations`
- Purpose: list Work History entries.
- Request: `branch`, `outputUrl`, `jobId`, `publicationId`, `operationType`, `status`, `summary`, `staged`, `originType`, `originURL`.
- Response: `ModelsListConversationsResponse` with `conversations`, `nextPageToken`, `previousPageToken`, and `error`.
- Notes: list permission applies to `Conversation`. `publicationId` narrows the result set. Omit `staged` for no filter; `staged=null` returns `400`.
- `curl`: `curl -H "Authorization: Bearer <token>" "https://api.doc.holiday/api/v1/conversations?publicationId=pub_123&staged=true"`
- `json`: `{"conversations":[{"id":"conv_123","status":"running"}],"nextPageToken":"","previousPageToken":""}`

### `POST /api/v1/conversations/`
- Purpose: create a Work History entry for a Publication.
- Request: `body`, `relevantLinks`, `changes`, `stage`, `publication`, `labels`.
- Response: `ModelsGetConversationResponse` with `id`, `status`, `staged`, `outputUrl`, `entries`, and the other Conversation fields.
- Notes: Doc Holiday resolves `publication` by name or ID, uses the Publication's docs repo `Connection` as the target, and enqueues the manual job after create-time permission checks and billing checks. This route is the handoff point for [GitHub Action](/g1-github-action.md) and [Coding agents](/g3-coding-agents.md).
- `curl`: `curl -X POST -H "Authorization: Bearer <token>" -H "Content-Type: application/json" -d '{"body":"Update the guide","publication":"docs","stage":true}' "https://api.doc.holiday/api/v1/conversations/"`
- `json`: `{"body":"Update the guide","publication":"docs","stage":true,"labels":["docs"]}`

### `GET /api/v1/conversations/{id}`
- Purpose: retrieve one Work History entry.
- Request: `id`.
- Response: `ModelsGetConversationResponse` with `id`, `status`, `branch`, `outputUrl`, `staged`, `excludedFiles`, `publicationName`, and `entries`.
- Notes: read permission applies to the `Conversation`, and the response includes the full Work History record for that entry.
- `curl`: `curl -H "Authorization: Bearer <token>" "https://api.doc.holiday/api/v1/conversations/conv_123"`
- `json`: `{"id":"conv_123","status":"open","staged":false,"entries":[]}`

### `PUT /api/v1/conversations/{id}`
- Purpose: update staged draft state or excluded files.
- Request: `staged`, `excludedFiles`.
- Response: `ModelsGetConversationResponse`.
- Notes: Doc Holiday rejects requests that set `staged` and `excludedFiles` together. When `staged` is omitted, it syncs excluded files on the working branch; when `staged` changes from `true` to `false`, it opens the draft as a pull request and clears `staged`.
- `curl`: `curl -X PUT -H "Authorization: Bearer <token>" -H "Content-Type: application/json" -d '{"staged":false}' "https://api.doc.holiday/api/v1/conversations/conv_123"`
- `json`: `{"staged":false}`

### `POST /api/v1/conversations/{id}/annotate`
- Purpose: queue annotation work for a Work History entry.
- Request: `id`.
- Response: `202 Accepted` with `ModelsAnnotateConversationResponse`.
- Notes: Doc Holiday schedules background annotation work and returns immediately.
- `curl`: `curl -X POST -H "Authorization: Bearer <token>" "https://api.doc.holiday/api/v1/conversations/conv_123/annotate"`
- `json`: `{}`

### `POST /api/v1/conversations/{id}/comments`
- Purpose: add a comment to an existing Work History entry.
- Request: `body`, `relevantLinks`, `changes`, `labels`, `workRequested`, `anchor`.
- Response: `ModelsGetConversationCommentResponse` with `id`, `message`, `workRequested`, `anchor`, `batchItemIds`, `batchedIntoIds`, and `replyIds`.
- Notes: `workRequested:false` takes the immediate discussion-comment path; `workRequested:true` or an omitted value queues work. `anchor` binds the comment to `filePath`, `anchoredFileSha`, and optional line range fields.
- `curl`: `curl -X POST -H "Authorization: Bearer <token>" -H "Content-Type: application/json" -d '{"body":"Please revise","workRequested":false}' "https://api.doc.holiday/api/v1/conversations/conv_123/comments"`
- `json`: `{"body":"Please revise","workRequested":false}`

### `POST /api/v1/conversations/{id}/comments/sendBatch`
- Purpose: add a batch reply for review.
- Request: `message`, `itemCommentIds`.
- Response: `200 OK` with no JSON body.
- Notes: Doc Holiday only accepts discussion-only comments from the same conversation, and it rejects work-requesting items.
- `curl`: `curl -X POST -H "Authorization: Bearer <token>" -H "Content-Type: application/json" -d '{"message":"Please review","itemCommentIds":["c1","c2"]}' "https://api.doc.holiday/api/v1/conversations/conv_123/comments/sendBatch"`
- `json`: `{"message":"Please review","itemCommentIds":["c1","c2"]}`

### `POST /api/v1/conversations/{id}/notify`
- Purpose: send a notification for the conversation.
- Request: `id`.
- Response: `ModelsNotifyConversationResponse`.
- Notes: the Publication must point at a notifier `Connection`, and the caller needs notify permission.
- `curl`: `curl -X POST -H "Authorization: Bearer <token>" "https://api.doc.holiday/api/v1/conversations/conv_123/notify"`
- `json`: `{}`

## `conversation_comments`

### `GET /api/v1/conversation_comments`
- Purpose: list comments across Work History entries.
- Request: `ids`, `conversationId`, `connectionId`, `workRequested`, `source`, `externalId`, `filePath`.
- Response: `ModelsListConversationCommentsResponse` with `comments`, `nextPageToken`, `previousPageToken`, and `error`.
- Notes: when `conversationId` is present, Doc Holiday checks read access on that Publication. Each comment can include `anchor`, `batchItemIds`, `batchedIntoIds`, and `replyIds`.
- `curl`: `curl -H "Authorization: Bearer <token>" "https://api.doc.holiday/api/v1/conversation_comments?conversationId=conv_123&workRequested=false"`
- `json`: `{"comments":[{"id":"c1","workRequested":false}],"nextPageToken":"","previousPageToken":""}`

### `PATCH /api/v1/conversation_comments/{id}`
- Purpose: edit one comment message.
- Request: `message`.
- Response: `ModelsGetConversationCommentResponse`.
- Notes: only the author can mutate the comment, and the comment must be discussion-only and not batched into an aggregate. Doc Holiday also checks update permission on the comment and read access on the Publication.
- `curl`: `curl -X PATCH -H "Authorization: Bearer <token>" -H "Content-Type: application/json" -d '{"message":"Updated note"}' "https://api.doc.holiday/api/v1/conversation_comments/c1"`
- `json`: `{"message":"Updated note"}`

### `DELETE /api/v1/conversation_comments/{id}`
- Purpose: remove one comment.
- Request: `id`.
- Response: `204 No Content`.
- Notes: the same author and mutability rules apply here: only the author can remove a comment that is neither work-requested nor batched.
- `curl`: `curl -X DELETE -H 'Authorization: Bearer …' /api/v1/conversation_comments/c1`
- `json`: `{}`

## `conversation_turns`

### `POST /api/v1/conversation_turns/{id}/retry`
- Purpose: retry one failed turn.
- Request: `id`.
- Response: `ModelsGetConversationTurnResponse` with `id`, `status`, `errorMessage`, `retryCount`, `request`, and `triggeringCommentId`.
- Notes: Doc Holiday accepts only turns in an error state, resets `status` to `running`, clears `errorMessage`, increments `retryCount`, and requeues the manual job after retry permission checks and Publication write access checks.
- `curl`: `curl -X POST -H 'Authorization: Bearer …' /api/v1/conversation_turns/turn_123/retry`
- `json`: `{"id":"turn_123","status":"running","retryCount":2}`