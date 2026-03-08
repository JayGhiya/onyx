## Engineering Workflow

| Stage | Command | Config File | Confidence |
|------------|------------------------|----------------------|------------|
| install | `npm ci` | package.json | 0.98 |
| build | `npm run build` | next.config.js | 0.98 |
| dev | `npm run dev` | next.config.js | 0.98 |
| test | `npm run test` | jest.config.js | 0.97 |
| lint | `npm run lint` | package.json | 0.97 |
| type_check | `npm run types:check` | tsconfig.types.json | 0.90 |

## Dependency Guide

This project is a **TypeScript / Next.js** web application managed with **npm**.
Full dependency purpose and usage details are maintained in [`dependencies_overview.md`](./dependencies_overview.md), which is the source-of-truth dependency catalog.

### Key dependency categories

| Category | Notable packages |
|---|---|
| Framework & Rendering | `next`, `react`, `react-dom` |
| Styling | `tailwindcss` (via config), `@headlessui/react`, `@headlessui/tailwindcss`, `tailwind-merge`, `tailwindcss-animate`, `class-variance-authority`, `clsx`, `autoprefixer`, `postcss`, `@emotion/stylis` |
| UI Primitives | Radix UI React Primitives (`@radix-ui/*`), `cmdk`, `vaul`, `lucide-react`, `@phosphor-icons/react`, `react-icons` |
| Icons & Media | `@phosphor-icons/react`, `lucide-react`, `react-icons`, `sharp` |
| Data Fetching & State | `swr`, `zustand` |
| Forms & Validation | `formik`, `yup`, `react-select`, `react-datepicker`, `react-day-picker` |
| Tables & Drag-and-Drop | `@tanstack/react-table`, `@dnd-kit/core` |
| Charts & Visualization | `recharts` |
| Markdown / Rich Text | `react-markdown`, `remark-gfm`, `remark-math`, `rehype-highlight`, `rehype-katex`, `rehype-sanitize`, `rehype-stringify`, `lowlight`, `highlight.js`, `mdast-util-find-and-replace` |
| Math & Code | `katex`, `highlight.js`, `lowlight` |
| Date & Time | `date-fns` |
| Animation | `motion` |
| Payments | `stripe`, `@stripe/stripe-js` |
| Monitoring & Analytics | `@sentry/nextjs`, `@sentry/tracing`, `posthog-js` |
| Theming | `next-themes` |
| Utilities | `lodash`, `clsx`, `uuid`, `semver`, `js-cookie`, `cookies-next`, `favicon-fetch`, `linguist-languages` |
| File Handling | `react-dropzone`, `docx-preview`, `pptxgenjs` |
| Loading States | `react-loader-spinner` |

> For full purpose and usage documentation of each dependency, see [`dependencies_overview.md`](./dependencies_overview.md).

## Business Logic Domain

The Onyx web application is an enterprise AI-powered knowledge management and search platform that enables organizations to connect to dozens of data sources (Slack, Google Drive, Confluence, Jira, GitHub, Salesforce, and many more) and query them through natural language chat and semantic search interfaces. The core domain revolves around configuring LLM providers and AI agents ("Personas"), indexing documents through connector pipelines, and delivering streaming AI responses with citations, tool calls (search, code execution, image generation, memory, web fetch), and deep research workflows. A secondary "Craft" (Build Mode) domain allows users to create and deploy AI-generated artifacts (web apps, documents, dashboards) through an agentic sandboxed code execution environment with session and file management. Administrative concerns include multi-tenant user management with RBAC, Slack/Discord bot integrations, MCP server tool connectivity, billing and licensing, embedding/reranking model configuration, and enterprise-level settings such as SCIM, SAML, and custom branding.

Full data model references are maintained in [`business_logic_references.md`](./business_logic_references.md).

## App Interfaces

Full interface details are maintained in [`app_interfaces.md`](./app_interfaces.md).

### Inbound HTTP Endpoints (Next.js Route Handlers)

| File | Method | Pattern / Notes |
|---|---|---|
| `src/app/api/[...path]/route.ts` | GET | Catch-all proxy — forwards any `GET /api/<path>` to the Onyx backend via `handleRequest` |
| `src/app/api/[...path]/route.ts` | POST | Catch-all proxy — forwards any `POST /api/<path>` to the Onyx backend via `handleRequest` |
| `src/app/api/[...path]/route.ts` | PUT | Catch-all proxy — forwards any `PUT /api/<path>` to the Onyx backend via `handleRequest` |
| `src/app/api/[...path]/route.ts` | PATCH | Catch-all proxy — forwards any `PATCH /api/<path>` to the Onyx backend via `handleRequest` |
| `src/app/api/[...path]/route.ts` | DELETE | Catch-all proxy — forwards any `DELETE /api/<path>` to the Onyx backend via `handleRequest` |
| `src/app/api/[...path]/route.ts` | HEAD | Catch-all proxy — forwards any `HEAD /api/<path>` to the Onyx backend via `handleRequest` |
| `src/app/api/[...path]/route.ts` | OPTIONS | Catch-all proxy — forwards any `OPTIONS /api/<path>` to the Onyx backend via `handleRequest` |
| `src/app/api/chat/mcp/oauth/callback/route.ts` | GET | MCP OAuth callback — exchanges `code`+`server_id` with backend `/api/mcp/oauth/callback`, then redirects to `/admin/actions/edit-mcp?server_id=<id>` (admin flow) or `/app` (user flow) |

### Internal State Stores (Zustand)

| File | Store Type | Notes |
|---|---|---|
| `src/app/app/stores/useChatSessionStore.ts` | `ChatSessionStore` | Manages chat session state for the main chat (`/app`) interface |
| `src/app/craft/hooks/useBuildSessionStore.ts` | `BuildSessionStore` | Manages build/artifact session state for the Craft (Build Mode) interface |
| `src/lib/hooks/useForcedTools.ts` | `ForcedToolsState` | Tracks forced tool IDs for tool-call overrides; exposes `setForcedToolIds`, `toggleForcedTool`, `clearForcedTools` |