# App Interfaces

This file is the source-of-truth interface catalog for the Onyx web application.
It is managed automatically — do not edit by hand.

---

## Inbound Interfaces

### HTTP Endpoints (Next.js Route Handlers)

#### `src/app/api/[...path]/route.ts` — Catch-All API Proxy

All methods delegate to the shared `handleRequest(request, path)` helper, which proxies requests to the configured Onyx backend (`NEXT_PUBLIC_ONYX_BACKEND_URL`).

| Method | Signature (line ref) | Description |
|---|---|---|
| GET | L7 | `GET /api/<...path>` → backend proxy |
| POST | L15 | `POST /api/<...path>` → backend proxy |
| PUT | L23 | `PUT /api/<...path>` → backend proxy |
| PATCH | L31 | `PATCH /api/<...path>` → backend proxy |
| DELETE | L39 | `DELETE /api/<...path>` → backend proxy |
| HEAD | L47 | `HEAD /api/<...path>` → backend proxy |
| OPTIONS | L55 | `OPTIONS /api/<...path>` → backend proxy |

#### `src/app/api/chat/mcp/oauth/callback/route.ts` — MCP OAuth Callback

| Method | Signature (line ref) | Description |
|---|---|---|
| GET | L6 | Handles the OAuth redirect from MCP provider. Reads `code`, `state`, `server_id` / `serverId`, `code_verifier` from query params. POSTs to backend `/api/mcp/oauth/callback` with `transport: "streamable-http"`. On success, redirects to `redirect_to` param, or `/admin/actions/edit-mcp?server_id=<id>` (admin flow, `admin=true`), or `/app` (user flow). Returns 400 on missing params or backend error, 500 on unexpected exception. |

---

## Outbound Interfaces

No outbound constructs detected.

---

## Internal State Stores (Zustand)

### `src/app/app/stores/useChatSessionStore.ts`

- **Store type:** `ChatSessionStore`
- **Created at:** L178 via `create<ChatSessionStore>()(…)`
- **Purpose:** Manages the full state of chat sessions within the main `/app` chat interface (messages, session metadata, streaming state, etc.).

### `src/app/craft/hooks/useBuildSessionStore.ts`

- **Store type:** `BuildSessionStore`
- **Created at:** L532 via `create<BuildSessionStore>()(…)`
- **Purpose:** Manages build/artifact session state for the Craft (Build Mode) interface, including agentic code generation sessions, file management, and sandbox lifecycle.

### `src/lib/hooks/useForcedTools.ts`

- **Store type:** `ForcedToolsState`
- **Created at:** L17 via `create<ForcedToolsState>((set, get) => (…))`
- **Purpose:** Tracks which tool IDs are currently "forced" (overriding normal tool selection) during a chat turn.
- **State shape:**
  - `forcedToolIds: string[]` — list of currently forced tool IDs
- **Actions:**
  - `setForcedToolIds(ids)` — replace the list
  - `toggleForcedTool(id)` — if `id` is already forced, clears all; otherwise sets `[id]` as the sole forced tool
  - `clearForcedTools()` — resets to `[]`