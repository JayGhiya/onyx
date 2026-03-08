# Business Logic References

This file is the source-of-truth catalog of data models, interfaces, hooks, services, and utilities that encode the core business logic of the Onyx web application.

## Domain Overview

The Onyx web application is an enterprise AI-powered knowledge management and search platform that enables organizations to connect to dozens of data sources (Slack, Google Drive, Confluence, Jira, GitHub, Salesforce, and many more) and query them through natural language chat and semantic search interfaces. The core domain revolves around configuring LLM providers and AI agents ("Personas"), indexing documents through connector pipelines, and delivering streaming AI responses with citations, tool calls (search, code execution, image generation, memory, web fetch), and deep research workflows. A secondary "Craft" (Build Mode) domain allows users to create and deploy AI-generated artifacts (web apps, documents, dashboards) through an agentic sandboxed code execution environment with session and file management. Administrative concerns include multi-tenant user management with RBAC, Slack/Discord bot integrations, MCP server tool connectivity, billing and licensing, embedding/reranking model configuration, and enterprise-level settings such as SCIM, SAML, and custom branding.

## Data Model & Logic Files

| File Path | Area |
|-----------|------|
| `lib/opal/src/types.ts` | OPAL shared types |
| `src/app/admin/agents/interfaces.ts` | Agent/Persona admin interfaces |
| `src/app/admin/agents/lib.ts` | Agent/Persona admin logic |
| `src/app/admin/api-key/types.ts` | API key types |
| `src/app/admin/bots/[bot-id]/lib.ts` | Slack/Discord bot configuration logic |
| `src/app/admin/bots/new/lib.ts` | New bot creation logic |
| `src/app/admin/configuration/image-generation/constants.ts` | Image generation constants |
| `src/app/admin/configuration/image-generation/forms/types.ts` | Image generation form types |
| `src/app/admin/configuration/web-search/WebProviderModalReducer.ts` | Web search provider modal reducer |
| `src/app/admin/configuration/web-search/connectProviderFlow.ts` | Web search provider connection flow |
| `src/app/admin/configuration/web-search/contentProviderUtils.ts` | Web search content provider utilities |
| `src/app/admin/configuration/web-search/searchProviderUtils.ts` | Web search provider utilities |
| `src/app/admin/connector/[ccPairId]/types.ts` | Connector pair types |
| `src/app/admin/discord-bot/types.ts` | Discord bot types |
| `src/app/admin/documents/sets/lib.ts` | Document set logic |
| `src/app/admin/embeddings/interfaces.ts` | Embedding model interfaces |
| `src/app/admin/federated/[id]/useFederatedConnector.ts` | Federated connector hook |
| `src/app/admin/kg/interfaces.ts` | Knowledge graph interfaces |
| `src/app/admin/scim/interfaces.ts` | SCIM provisioning interfaces |
| `src/app/admin/token-rate-limits/types.ts` | Token rate limit types |
| `src/app/app/components/folders/interfaces.ts` | Chat folder interfaces |
| `src/app/app/interfaces.ts` | Core app interfaces |
| `src/app/app/message/messageComponents/hooks/useMessageSwitching.ts` | Message switching hook |
| `src/app/app/message/messageComponents/hooks/usePacketAnimationAndCollapse.ts` | Packet animation hook |
| `src/app/app/message/messageComponents/interfaces.ts` | Message component interfaces |
| `src/app/app/message/messageComponents/timeline/hooks/packetProcessor.ts` | Timeline packet processor |
| `src/app/app/message/messageComponents/timeline/hooks/usePacedTurnGroups.ts` | Paced turn groups hook |
| `src/app/app/message/messageComponents/timeline/hooks/usePacketProcessor.ts` | Packet processor hook |
| `src/app/app/message/messageComponents/timeline/hooks/useTimelineExpansion.ts` | Timeline expansion hook |
| `src/app/app/message/messageComponents/timeline/hooks/useTimelineHeader.ts` | Timeline header hook |
| `src/app/app/message/messageComponents/timeline/hooks/useTimelineMetrics.ts` | Timeline metrics hook |
| `src/app/app/message/messageComponents/timeline/hooks/useTimelineStepState.ts` | Timeline step state hook |
| `src/app/app/message/messageComponents/timeline/hooks/useTimelineUIState.ts` | Timeline UI state hook |
| `src/app/app/message/messageComponents/timeline/primitives/tokens.ts` | Timeline primitive tokens |
| `src/app/app/message/messageComponents/timeline/renderers/fetch/fetchStateUtils.ts` | Fetch state utilities |
| `src/app/app/message/messageComponents/timeline/renderers/memory/memoryStateUtils.ts` | Memory state utilities |
| `src/app/app/message/messageComponents/timeline/renderers/search/searchStateUtils.ts` | Search state utilities |
| `src/app/app/message/messageComponents/timeline/transformers.ts` | Timeline transformers |
| `src/app/app/projects/projectsService.ts` | Projects service |
| `src/app/app/services/messageTree.ts` | Message tree service |
| `src/app/app/services/streamingModels.ts` | Streaming models service |
| `src/app/app/stores/useChatSessionStore.ts` | Chat session store |
| `src/app/craft/constants/exampleBuildPrompts.ts` | Craft example build prompts |
| `src/app/craft/hooks/useBuildConnectors.ts` | Craft build connectors hook |
| `src/app/craft/hooks/useBuildSessionController.ts` | Craft build session controller |
| `src/app/craft/hooks/useBuildSessionStore.ts` | Craft build session store |
| `src/app/craft/hooks/usePreProvisionPolling.ts` | Craft pre-provision polling hook |
| `src/app/craft/hooks/useUsageLimits.ts` | Craft usage limits hook |
| `src/app/craft/onboarding/constants.ts` | Craft onboarding constants |
| `src/app/craft/onboarding/types.ts` | Craft onboarding types |
| `src/app/craft/services/apiServices.ts` | Craft API services |
| `src/app/craft/types/displayTypes.ts` | Craft display types |
| `src/app/craft/types/streamingTypes.ts` | Craft streaming types |
| `src/app/craft/types/user-library.ts` | Craft user library types |
| `src/app/craft/utils/packetTypes.ts` | Craft packet types |
| `src/app/craft/v1/configure/utils/createBuildConnector.ts` | Craft build connector factory |
| `src/app/ee/admin/groups/types.ts` | EE admin group types |
| `src/app/ee/admin/performance/lib.ts` | EE performance admin logic |
| `src/app/ee/admin/performance/query-history/types.ts` | Query history types |
| `src/app/ee/admin/performance/usage/types.ts` | Usage analytics types |
| `src/app/ee/admin/standard-answer/lib.ts` | Standard answer admin logic |
| `src/app/mcp/[[...path]]/route.ts` | MCP proxy route |
| `src/components/admin/connectors/types.ts` | Connector admin types |
| `src/components/credentials/types.ts` | Credential types |
| `src/components/table/interfaces.ts` | Table component interfaces |
| `src/hooks/appNavigation.ts` | App navigation hook |
| `src/hooks/useAdminPersonas.ts` | Admin personas hook |
| `src/hooks/useAppFocus.ts` | App focus hook |
| `src/hooks/useBrowserInfo.ts` | Browser info hook |
| `src/hooks/useChatController.ts` | Chat controller hook |
| `src/hooks/useChatSessionController.ts` | Chat session controller hook |
| `src/hooks/useChatSessions.ts` | Chat sessions hook |
| `src/hooks/useCodeInterpreter.ts` | Code interpreter hook |
| `src/hooks/useContainerCenter.ts` | Container center hook |
| `src/hooks/useContentSize.ts` | Content size hook |
| `src/hooks/useDeepResearchToggle.ts` | Deep research toggle hook |
| `src/hooks/useImageDropzone.ts` | Image dropzone hook |
| `src/hooks/useMemoryManager.ts` | Memory manager hook |
| `src/hooks/usePaginatedFetch.ts` | Paginated fetch hook |
| `src/hooks/useScreenSize.ts` | Screen size hook |
| `src/hooks/useServerTools.ts` | Server tools hook |
| `src/hooks/useShareableGroups.ts` | Shareable groups hook |
| `src/hooks/useShareableUsers.ts` | Shareable users hook |
| `src/hooks/useShowOnboarding.ts` | Show onboarding hook |
| `src/hooks/useTags.ts` | Tags hook |
| `src/hooks/useToast.ts` | Toast notification hook |
| `src/hooks/useUserPersonalization.ts` | User personalization hook |
| `src/hooks/useUsers.ts` | Users hook |
| `src/interfaces/llm.ts` | LLM interfaces |
| `src/interfaces/onboarding.ts` | Onboarding interfaces |
| `src/interfaces/settings.ts` | Settings interfaces |
| `src/lib/admin-routes.ts` | Admin route definitions |
| `src/lib/admin/code-interpreter/svc.ts` | Code interpreter service |
| `src/lib/appSidebarSS.ts` | App sidebar server-side logic |
| `src/lib/auth/requireAuth.ts` | Auth guard utility |
| `src/lib/billing/interfaces.ts` | Billing interfaces |
| `src/lib/build/client.ts` | Build/Craft client |
| `src/lib/configuration/imageConfigurationService.ts` | Image configuration service |
| `src/lib/connectors/credentials.ts` | Connector credentials logic |
| `src/lib/connectors/fileTypes.ts` | Connector file type definitions |
| `src/lib/constants/chatBackgrounds.ts` | Chat background constants |
| `src/lib/contains.ts` | Contains utility |
| `src/lib/fileConnector.ts` | File connector logic |
| `src/lib/headers/fetchHeaderDataSS.ts` | Server-side header fetch |
| `src/lib/hierarchy/interfaces.ts` | Hierarchy interfaces |
| `src/lib/hooks.ts` | Shared lib hooks |
| `src/lib/hooks/useCaptcha.ts` | CAPTCHA hook |
| `src/lib/hooks/useCustomAnalyticsEnabled.ts` | Custom analytics hook |
| `src/lib/hooks/useForcedTools.ts` | Forced tools hook |
| `src/lib/hooks/useToolOAuthStatus.ts` | Tool OAuth status hook |
| `src/lib/languages.ts` | Language definitions |
| `src/lib/search/interfaces.ts` | Search interfaces |
| `src/lib/sources.ts` | Data source definitions |
| `src/lib/tools/interfaces.ts` | Tool interfaces |
| `src/lib/tools/mcpService.ts` | MCP service |
| `src/lib/tools/openApiService.ts` | OpenAPI tool service |
| `src/lib/types.ts` | Core lib types |
| `src/lib/urlBuilder.ts` | URL builder utility |
| `src/lib/user.ts` | User utilities |
| `src/lib/userSS.ts` | Server-side user utilities |
| `src/refresh-components/commandmenu/types.ts` | Command menu types |
| `src/refresh-components/form/types.ts` | Form types |
| `src/refresh-components/inputs/InputComboBox/hooks.ts` | ComboBox hooks |
| `src/refresh-components/inputs/InputComboBox/types.ts` | ComboBox types |
| `src/refresh-components/inputs/InputComboBox/utils/aria.ts` | ComboBox ARIA utilities |
| `src/refresh-components/inputs/InputComboBox/utils/validation.ts` | ComboBox validation utilities |
| `src/refresh-components/inputs/styles.ts` | Input styles |
| `src/refresh-components/popovers/interfaces.ts` | Popover interfaces |
| `src/refresh-components/table/columns.ts` | Table column definitions |
| `src/refresh-components/table/hooks/useColumnWidths.ts` | Column widths hook |
| `src/refresh-components/table/hooks/useDataTable.ts` | Data table hook |
| `src/refresh-components/table/hooks/useDraggableRows.ts` | Draggable rows hook |
| `src/refresh-components/table/types.ts` | Table types |
| `src/sections/modals/PreviewModal/interfaces.ts` | Preview modal interfaces |
| `src/sections/modals/llmConfig/formUtils.ts` | LLM config form utilities |
| `src/sections/onboarding/components/llmConnectionHelpers.ts` | LLM connection helpers |
| `src/sections/onboarding/constants.ts` | Onboarding constants |
| `src/sections/sidebar/sidebarUtils.ts` | Sidebar utilities |
| `src/sections/sidebar/useChatSearchOptimistic.ts` | Chat search optimistic hook |
| `tests/e2e/admin/admin_pages.spec.ts` | E2E admin pages tests |
| `tests/e2e/admin/discord-bot/fixtures.ts` | E2E Discord bot fixtures |
| `tests/e2e/admin/llm_provider_setup.spec.ts` | E2E LLM provider setup tests |
| `tests/e2e/admin/scim/fixtures.ts` | E2E SCIM fixtures |
| `tests/e2e/chat/chat_message_rendering.spec.ts` | E2E chat message rendering tests |
| `tests/e2e/chat/llm_runtime_selection.spec.ts` | E2E LLM runtime selection tests |
| `tests/e2e/mcp/mcp_oauth_flow.spec.ts` | E2E MCP OAuth flow tests |
| `tests/e2e/utils/agentUtils.ts` | E2E agent test utilities |
| `tests/e2e/utils/chatStream.ts` | E2E chat stream utilities |
| `tests/e2e/utils/mcpServer.ts` | E2E MCP server utilities |
| `tests/e2e/utils/visualRegression.ts` | E2E visual regression utilities |