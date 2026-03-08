# Business Logic References

This file catalogs the key data model and business-logic source files for the Onyx backend. Each entry maps a file path to its domain area.

## Domain Overview

Onyx is an enterprise-grade AI-powered knowledge management and search platform that ingests documents from a wide range of external sources — including Confluence, Google Drive, Slack, SharePoint, GitHub, Notion, Salesforce, and many others — and indexes them into a vector/keyword search backend (Vespa and OpenSearch) to enable semantically rich retrieval. The core user-facing experience is an LLM-backed chat interface where configurable AI "personas" (assistants) can answer questions by citing retrieved document chunks, calling tools (web search, image generation, code execution, MCP integrations), and optionally performing deep research across the knowledge base. The platform includes robust role-based access control, per-document permission syncing, multi-tenancy, federated connectors (e.g., real-time Slack search), knowledge graph extraction, and an agentic "Build" feature where users interact with a sandboxed coding agent to create web applications. Supporting infrastructure encompasses background indexing pipelines with Celery, token rate limiting, user memory/personalization, and extensive admin tooling for managing LLM providers, embedding models, OAuth flows, and connector credentials.

## Data Model & Key File References

| File Path | Domain Area |
|-----------|-------------|
| `onyx/access/models.py` | Access control models |
| `onyx/auth/api_key.py` | API key authentication |
| `onyx/auth/captcha.py` | CAPTCHA verification |
| `onyx/auth/users.py` | User authentication & management |
| `onyx/background/celery/celery_utils.py` | Celery background task utilities |
| `onyx/background/celery/tasks/docprocessing/tasks.py` | Document processing Celery tasks |
| `onyx/background/celery/tasks/models.py` | Celery task models |
| `onyx/background/celery/tasks/monitoring/tasks.py` | Celery monitoring tasks |
| `onyx/background/indexing/job_client.py` | Indexing job client |
| `onyx/background/indexing/models.py` | Indexing background models |
| `onyx/background/periodic_poller.py` | Periodic background polling |
| `onyx/chat/compression.py` | Chat context compression |
| `onyx/chat/models.py` | Chat domain models |
| `onyx/chat/process_message.py` | Chat message processing pipeline |
| `onyx/configs/embedding_configs.py` | Embedding configuration |
| `onyx/connectors/axero/connector.py` | Axero connector |
| `onyx/connectors/coda/connector.py` | Coda connector |
| `onyx/connectors/confluence/models.py` | Confluence models |
| `onyx/connectors/confluence/utils.py` | Confluence utilities |
| `onyx/connectors/discourse/connector.py` | Discourse connector |
| `onyx/connectors/drupal_wiki/models.py` | Drupal Wiki models |
| `onyx/connectors/github/connector.py` | GitHub connector |
| `onyx/connectors/github/models.py` | GitHub models |
| `onyx/connectors/google_drive/doc_conversion.py` | Google Drive document conversion |
| `onyx/connectors/google_drive/models.py` | Google Drive models |
| `onyx/connectors/google_drive/section_extraction.py` | Google Drive section extraction |
| `onyx/connectors/highspot/connector.py` | Highspot connector |
| `onyx/connectors/imap/connector.py` | IMAP email connector |
| `onyx/connectors/imap/models.py` | IMAP models |
| `onyx/connectors/interfaces.py` | Connector base interfaces |
| `onyx/connectors/microsoft_graph_env.py` | Microsoft Graph environment config |
| `onyx/connectors/mock_connector/connector.py` | Mock connector (testing) |
| `onyx/connectors/models.py` | Shared connector models |
| `onyx/connectors/notion/connector.py` | Notion connector |
| `onyx/connectors/registry.py` | Connector registry |
| `onyx/connectors/salesforce/utils.py` | Salesforce utilities |
| `onyx/connectors/sharepoint/connector.py` | SharePoint connector |
| `onyx/connectors/slack/connector.py` | Slack connector |
| `onyx/connectors/teams/models.py` | Microsoft Teams models |
| `onyx/connectors/zendesk/connector.py` | Zendesk connector |
| `onyx/connectors/zulip/schemas.py` | Zulip schemas |
| `onyx/context/search/federated/models.py` | Federated search models |
| `onyx/context/search/federated/slack_search.py` | Federated Slack search |
| `onyx/context/search/models.py` | Search context models |
| `onyx/db/indexing_coordination.py` | Indexing coordination DB layer |
| `onyx/db/memory.py` | User memory DB layer |
| `onyx/db/models.py` | Core ORM / database models |
| `onyx/db/projects.py` | Projects DB layer |
| `onyx/db/usage.py` | Usage tracking DB layer |
| `onyx/db/utils.py` | Database utilities |
| `onyx/deep_research/models.py` | Deep research models |
| `onyx/deep_research/utils.py` | Deep research utilities |
| `onyx/document_index/interfaces.py` | Document index interfaces |
| `onyx/document_index/interfaces_new.py` | Document index interfaces (new) |
| `onyx/document_index/opensearch/client.py` | OpenSearch client |
| `onyx/document_index/opensearch/schema.py` | OpenSearch schema |
| `onyx/document_index/vespa/index.py` | Vespa index operations |
| `onyx/document_index/vespa/vespa_document_index.py` | Vespa document index |
| `onyx/evals/models.py` | Evaluation models |
| `onyx/federated_connectors/federated_retrieval.py` | Federated connector retrieval |
| `onyx/federated_connectors/models.py` | Federated connector models |
| `onyx/federated_connectors/registry.py` | Federated connector registry |
| `onyx/federated_connectors/slack/models.py` | Federated Slack models |
| `onyx/file_processing/html_utils.py` | HTML file processing utilities |
| `onyx/file_store/document_batch_storage.py` | Document batch storage |
| `onyx/file_store/models.py` | File store models |
| `onyx/image_gen/interfaces.py` | Image generation interfaces |
| `onyx/image_gen/providers/vertex_img_gen.py` | Vertex AI image generation |
| `onyx/indexing/indexing_pipeline.py` | Indexing pipeline |
| `onyx/indexing/models.py` | Indexing models |
| `onyx/kg/models.py` | Knowledge graph models |
| `onyx/llm/interfaces.py` | LLM interfaces |
| `onyx/llm/model_name_parser.py` | LLM model name parsing |
| `onyx/llm/model_response.py` | LLM model response types |
| `onyx/llm/models.py` | LLM domain models |
| `onyx/llm/override_models.py` | LLM override models |
| `onyx/llm/prompt_cache/models.py` | Prompt cache models |
| `onyx/llm/well_known_providers/auto_update_models.py` | Auto-update LLM provider models |
| `onyx/llm/well_known_providers/models.py` | Well-known LLM provider models |
| `onyx/onyxbot/discord/handle_message.py` | Discord bot message handling |
| `onyx/onyxbot/slack/models.py` | Slack bot models |
| `onyx/redis/redis_connector_delete.py` | Redis connector delete state |
| `onyx/redis/redis_connector_doc_perm_sync.py` | Redis doc permission sync state |
| `onyx/redis/redis_connector_ext_group_sync.py` | Redis external group sync state |
| `onyx/redis/redis_connector_index.py` | Redis connector index state |
| `onyx/redis/redis_connector_prune.py` | Redis connector prune state |
| `onyx/redis/redis_hierarchy.py` | Redis hierarchy management |
| `onyx/server/api_key/models.py` | API key server models |
| `onyx/server/documents/connector.py` | Document connector API |
| `onyx/server/documents/models.py` | Document server models |
| `onyx/server/documents/standard_oauth.py` | Standard OAuth for documents |
| `onyx/server/evals/models.py` | Evaluation server models |
| `onyx/server/features/build/api/models.py` | Build feature API models |
| `onyx/server/features/build/api/packets.py` | Build feature API packets |
| `onyx/server/features/build/api/user_library.py` | Build feature user library |
| `onyx/server/features/build/sandbox/kubernetes/internal/acp_exec_client.py` | Build sandbox Kubernetes ACP exec client |
| `onyx/server/features/build/sandbox/local/agent_client.py` | Build sandbox local agent client |
| `onyx/server/features/build/sandbox/models.py` | Build sandbox models |
| `onyx/server/features/default_assistant/models.py` | Default assistant models |
| `onyx/server/features/document_set/models.py` | Document set models |
| `onyx/server/features/hierarchy/models.py` | Hierarchy feature models |
| `onyx/server/features/input_prompt/models.py` | Input prompt models |
| `onyx/server/features/mcp/api.py` | MCP feature API |
| `onyx/server/features/mcp/models.py` | MCP feature models |
| `onyx/server/features/oauth_config/models.py` | OAuth config models |
| `onyx/server/features/password/models.py` | Password feature models |
| `onyx/server/features/persona/api.py` | Persona feature API |
| `onyx/server/features/persona/models.py` | Persona feature models |
| `onyx/server/features/projects/api.py` | Projects feature API |
| `onyx/server/features/projects/models.py` | Projects feature models |
| `onyx/server/features/projects/projects_file_utils.py` | Projects file utilities |
| `onyx/server/features/release_notes/models.py` | Release notes models |
| `onyx/server/features/tool/api.py` | Tool feature API |
| `onyx/server/features/tool/models.py` | Tool feature models |
| `onyx/server/features/tool/tool_visibility.py` | Tool visibility control |
| `onyx/server/features/user_oauth_token/api.py` | User OAuth token API |
| `onyx/server/features/web_search/models.py` | Web search feature models |
| `onyx/server/federated/models.py` | Federated server models |
| `onyx/server/kg/models.py` | Knowledge graph server models |
| `onyx/server/manage/code_interpreter/models.py` | Code interpreter admin models |
| `onyx/server/manage/discord_bot/models.py` | Discord bot admin models |
| `onyx/server/manage/embedding/models.py` | Embedding admin models |
| `onyx/server/manage/image_generation/models.py` | Image generation admin models |
| `onyx/server/manage/llm/models.py` | LLM admin models |
| `onyx/server/manage/models.py` | General admin models |
| `onyx/server/manage/opensearch_migration/models.py` | OpenSearch migration admin models |
| `onyx/server/manage/users.py` | User management admin API |
| `onyx/server/manage/web_search/models.py` | Web search admin models |
| `onyx/server/models.py` | General server models |
| `onyx/server/onyx_api/models.py` | Onyx public API models |
| `onyx/server/pat/models.py` | Personal access token models |
| `onyx/server/query_and_chat/chat_backend.py` | Chat backend query handling |
| `onyx/server/query_and_chat/models.py` | Query and chat models |
| `onyx/server/query_and_chat/placement.py` | Query placement logic |
| `onyx/server/query_and_chat/streaming_models.py` | Streaming response models |
| `onyx/server/saml.py` | SAML authentication server |
| `onyx/server/settings/models.py` | Settings models |
| `onyx/server/tenant_usage_limits.py` | Tenant usage limits |
| `onyx/server/token_rate_limits/models.py` | Token rate limit models |
| `onyx/tools/models.py` | Tool domain models |
| `onyx/tools/tool_constructor.py` | Tool construction logic |
| `onyx/tools/tool_implementations/custom/openapi_parsing.py` | Custom tool OpenAPI parsing |
| `onyx/tools/tool_implementations/images/models.py` | Image tool models |
| `onyx/tools/tool_implementations/mcp/mcp_client.py` | MCP tool client |
| `onyx/tools/tool_implementations/memory/memory_tool.py` | Memory tool implementation |
| `onyx/tools/tool_implementations/memory/models.py` | Memory tool models |
| `onyx/tools/tool_implementations/open_url/firecrawl.py` | Firecrawl URL tool |
| `onyx/tools/tool_implementations/open_url/models.py` | Open URL tool models |
| `onyx/tools/tool_implementations/open_url/open_url_tool.py` | Open URL tool implementation |
| `onyx/tools/tool_implementations/open_url/snippet_matcher.py` | URL snippet matching |
| `onyx/tools/tool_implementations/python/code_interpreter_client.py` | Python code interpreter client |
| `onyx/tools/tool_implementations/web_search/models.py` | Web search tool models |
| `onyx/utils/file.py` | File utilities |