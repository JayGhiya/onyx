# App Interfaces

Full catalog of inbound HTTP endpoints, outbound LLM inference calls, and internal scheduled tasks for the Onyx backend.

---

## Inbound: HTTP Endpoints (FastAPI)

### `auth/users.py`
| Line | Method | Path |
|------|--------|------|
| L1250 | POST | `/logout` (per-backend, `auth:{backend.name}.logout`) |
| L1288 | POST | `/refresh` (per-backend, `auth:{backend.name}.refresh`) |
| L1685 | GET | `/authorize` (OAuth, `oauth:{oauth_client.name}.{backend.name}.authorize`) |
| L1757 | GET | `/callback` (OAuth) |

### `server/api_key/api.py`
| Line | Method | Path |
|------|--------|------|
| L20 | GET | `` |
| L28 | POST | `` |
| L37 | POST | `/{api_key_id}/regenerate` |
| L46 | PATCH | `/{api_key_id}` |
| L56 | DELETE | `/{api_key_id}` |

### `server/documents/cc_pair.py`
| Line | Method | Path |
|------|--------|------|
| L77 | GET | `/admin/cc-pair/{cc_pair_id}/index-attempts` |
| L113 | GET | `/admin/cc-pair/{cc_pair_id}/permission-sync-attempts` |
| L151 | GET | `/admin/cc-pair/{cc_pair_id}` |
| L244 | PUT | `/admin/cc-pair/{cc_pair_id}/status` |
| L328 | PUT | `/admin/cc-pair/{cc_pair_id}/name` |
| L357 | PUT | `/admin/cc-pair/{cc_pair_id}/property` |
| L397 | GET | `/admin/cc-pair/{cc_pair_id}/last_pruned` |
| L418 | POST | `/admin/cc-pair/{cc_pair_id}/prune` |
| L471 | GET | `/admin/cc-pair/{cc_pair_id}/get-docs-sync-status` |
| L484 | GET | `/admin/cc-pair/{cc_pair_id}/errors` |
| L525 | PUT | `/connector/{connector_id}/credential/{credential_id}` |
| L607 | DELETE | `/connector/{connector_id}/credential/{credential_id}` |

### `server/documents/connector.py`
| Line | Method | Path |
|------|--------|------|
| L176 | GET | `/admin/connector/gmail/app-credential` |
| L186 | PUT | `/admin/connector/gmail/app-credential` |
| L200 | DELETE | `/admin/connector/gmail/app-credential` |
| L216 | GET | `/admin/connector/google-drive/app-credential` |
| L228 | PUT | `/admin/connector/google-drive/app-credential` |
| L242 | DELETE | `/admin/connector/google-drive/app-credential` |
| L258 | GET | `/admin/connector/gmail/service-account-key` |
| L274 | PUT | `/admin/connector/gmail/service-account-key` |
| L288 | DELETE | `/admin/connector/gmail/service-account-key` |
| L304 | GET | `/admin/connector/google-drive/service-account-key` |
| L320 | PUT | `/admin/connector/google-drive/service-account-key` |
| L334 | DELETE | `/admin/connector/google-drive/service-account-key` |
| L350 | PUT | `/admin/connector/google-drive/service-account-credential` |
| L377 | PUT | `/admin/connector/gmail/service-account-credential` |
| L403 | GET | `/admin/connector/google-drive/check-auth/{credential_id}` |
| L613 | POST | `/admin/connector/file/upload` |
| L621 | GET | `/admin/connector/{connector_id}/files` |
| L688 | POST | `/admin/connector/{connector_id}/files/update` |
| L904 | GET | `/admin/connector` |
| L937 | GET | `/admin/connector/failed-indexing-status` |
| L1025 | GET | `/admin/connector/status` |
| L1077 | POST | `/admin/connector/indexing-status` |
| L1508 | POST | `/admin/connector` |
| L1547 | POST | `/admin/connector-with-mock-credential` |
| L1629 | PATCH | `/admin/connector/{connector_id}` |
| L1676 | DELETE | `/admin/connector/{connector_id}` |
| L1696 | POST | `/admin/connector/run-once` |
| L1759 | GET | `/connector/gmail/authorize/{credential_id}` |
| L1773 | GET | `/connector/google-drive/authorize/{credential_id}` |
| L1789 | GET | `/connector/gmail/callback` |
| L1819 | GET | `/connector/google-drive/callback` |
| L1850 | GET | `/connector` |
| L1865 | GET | `/indexed-sources` |
| L1876 | GET | `/connector/{connector_id}` |
| L1905 | POST | `/connector-request` |
| L1991 | GET | `/connector-status` |

### `server/documents/credential.py`
| Line | Method | Path |
|------|--------|------|
| L56 | GET | `/admin/credential` |
| L73 | GET | `/admin/similar-credentials/{source_type}` |
| L95 | DELETE | `/admin/credential/{credential_id}` |
| L108 | PUT | `/admin/credential/swap` |
| L135 | POST | `/credential` |
| L162 | POST | `/credential/private-key` |
| L229 | GET | `/credential` |
| L241 | GET | `/credential/{credential_id}` |
| L262 | PUT | `/admin/credential/{credential_id}` |
| L286 | PUT | `/admin/credential/private-key/{credential_id}` |
| L333 | PATCH | `/credential/{credential_id}` |
| L369 | DELETE | `/credential/{credential_id}` |
| L386 | DELETE | `/credential/force/{credential_id}` |

### `server/documents/document.py`
| Line | Method | Path |
|------|--------|------|
| L29 | GET | `/document-size-info` |
| L73 | GET | `/chunk-info` |

### `server/documents/standard_oauth.py`
| Line | Method | Path |
|------|--------|------|
| L87 | GET | `/authorize/{source}` |
| L138 | GET | `/callback/{source}` |
| L201 | GET | `/details/{source}` |

### `server/features/build/api/api.py`
| Line | Method | Path |
|------|--------|------|
| L70 | GET | `/limit` |
| L84 | GET | `/connectors` |
| L412 | GET | `/sessions/{session_id}/webapp` (public) |
| L413 | GET | `/sessions/{session_id}/webapp/{path:path}` (public) |
| L447 | POST | `/sandbox/reset` |

### `server/features/build/api/messages_api.py`
| Line | Method | Path |
|------|--------|------|
| L53 | GET | `/sessions/{session_id}/messages` |
| L75 | POST | `/sessions/{session_id}/send-message` |

### `server/features/build/api/sessions_api.py`
| Line | Method | Path |
|------|--------|------|
| L66 | GET | `` |
| L88 | POST | `` |
| L157 | GET | `/{session_id}` |
| L193 | GET | `/{session_id}/pre-provisioned-check` |
| L228 | POST | `/{session_id}/generate-name` |
| L245 | POST | `/{session_id}/generate-suggestions` |
| L280 | PUT | `/{session_id}/name` |
| L300 | PATCH | `/{session_id}/public` |
| L319 | DELETE | `/{session_id}` |
| L356 | POST | `/{session_id}/restore` |
| L535 | GET | `/{session_id}/artifacts` |
| L555 | GET | `/{session_id}/files` |
| L593 | GET | `/{session_id}/artifacts/{path:path}` |
| L644 | GET | `/{session_id}/export-docx/{path:path}` |
| L686 | GET | `/{session_id}/pptx-preview/{path:path}` |
| L713 | GET | `/{session_id}/webapp-info` |
| L735 | GET | `/{session_id}/webapp/download` |
| L765 | GET | `/{session_id}/download-directory/{path:path}` |
| L802 | POST | `/{session_id}/upload` |
| L853 | DELETE | `/{session_id}/files/{path:path}` |

### `server/features/build/api/user_library.py`
| Line | Method | Path |
|------|--------|------|
| L283 | GET | `/tree` |
| L322 | POST | `/upload` |
| L439 | POST | `/upload-zip` |
| L609 | POST | `/directories` |
| L658 | PATCH | `/files/{document_id}/toggle` |
| L711 | DELETE | `/files/{document_id}` |

### `server/features/default_assistant/api.py`
| Line | Method | Path |
|------|--------|------|
| L23 | GET | `/configuration` |
| L47 | PATCH | `` |

### `server/features/document_set/api.py`
| Line | Method | Path |
|------|--------|------|
| L34 | POST | `/admin/document-set` |
| L69 | PATCH | `/admin/document-set` |
| L110 | DELETE | `/admin/document-set/{document_set_id}` |
| L160 | GET | `/document-set` |
| L174 | GET | `/document-set-public` |

### `server/features/hierarchy/api.py`
| Line | Method | Path |
|------|--------|------|
| L65 | GET | `HIERARCHY_NODES_LIST_PATH` |
| L92 | POST | `HIERARCHY_NODE_DOCUMENTS_PATH` |

### `server/features/input_prompt/api.py`
| Line | Method | Path | Router |
|------|--------|------|--------|
| L29 | GET | `` | basic |
| L43 | GET | `/{input_prompt_id}` | basic |
| L58 | POST | `` | basic |
| L81 | PATCH | `/{input_prompt_id}` | basic |
| L105 | DELETE | `/{input_prompt_id}` | basic |
| L123 | DELETE | `/{input_prompt_id}` | admin |
| L138 | POST | `/{input_prompt_id}/hide` | basic |

### `server/features/mcp/api.py`
| Line | Method | Path | Router |
|------|--------|------|--------|
| L349 | POST | `/oauth/connect` | admin |
| L359 | POST | `/oauth/connect` | user |
| L571 | POST | `/oauth/callback` | user |
| L656 | POST | `/user-credentials` | user |
| L984 | GET | `/servers/persona/{assistant_id}` | user |
| L1013 | GET | `/servers` | user |
| L1069 | GET | `/server/{server_id}/tools` | admin |
| L1083 | GET | `/server/{server_id}/tools/snapshots` | admin |
| L1141 | GET | `/server/{server_id}/tools` | user |
| L1572 | GET | `/servers/{server_id}` | admin |
| L1600 | GET | `/tools` | admin |
| L1618 | PATCH | `/server/{server_id}/status` | admin |
| L1646 | GET | `/servers` | admin |
| L1671 | GET | `/server/{server_id}/db-tools` | admin |
| L1716 | POST | `/servers/create` | admin |
| L1778 | POST | `/servers/update` | admin |
| L1830 | POST | `/server` | admin |
| L1869 | PATCH | `/server/{server_id}` | admin |
| L1901 | DELETE | `/server/{server_id}` | admin |

### `server/features/notifications/api.py`
| Line | Method | Path |
|------|--------|------|
| L23 | GET | `` |
| L58 | POST | `/{notification_id}/dismiss` |

### `server/features/oauth_config/api.py`
| Line | Method | Path | Router |
|------|--------|------|--------|
| L62 | POST | `/create` | admin |
| L85 | GET | `` | admin |
| L95 | GET | `/{oauth_config_id}` | admin |
| L110 | PUT | `/{oauth_config_id}` | admin |
| L137 | DELETE | `/{oauth_config_id}` | admin |
| L154 | POST | `/initiate` | user |
| L190 | POST | `/callback` | user |
| L252 | DELETE | `/{oauth_config_id}/token` | user |

### `server/features/password/api.py`
| Line | Method | Path |
|------|--------|------|
| L21 | POST | `/change-password` |
| L44 | POST | `/reset_password` |

### `server/features/persona/api.py`
| Line | Method | Path | Router |
|------|--------|------|--------|
| L137 | PATCH | `/{persona_id}/visible` | admin |
| L152 | PATCH | `/{persona_id}/public` | basic |
| L171 | PATCH | `/{persona_id}/featured` | admin |
| L190 | PATCH | `/display-priorities` | admin_agents |
| L208 | GET | `` | admin |
| L223 | GET | `` | admin_agents |
| L268 | PATCH | `/{persona_id}/undelete` | admin |
| L282 | POST | `/upload-image` | admin |
| L301 | POST | `` | basic |
| L330 | PATCH | `/{persona_id}` | basic |
| L353 | GET | `/labels` | basic |
| L364 | POST | `/labels` | basic |
| L381 | PATCH | `/label/{label_id}` | admin |
| L395 | DELETE | `/label/{label_id}` | admin |
| L412 | PATCH | `/{persona_id}/share` | basic |
| L437 | DELETE | `/{persona_id}` | basic |
| L450 | GET | `` | basic |
| L470 | GET | `` | agents |
| L518 | GET | `/{persona_id}` | basic |

### `server/features/projects/api.py`
| Line | Method | Path |
|------|--------|------|
| L99 | GET | `` |
| L111 | POST | `/create` |
| L126 | POST | `/file/upload` |
| L168 | GET | `/{project_id}` |
| L185 | GET | `/files/{project_id}` |
| L206 | DELETE | `/{project_id}/files/{file_id}` |
| L247 | POST | `/{project_id}/files/{file_id}` |
| L296 | GET | `/{project_id}/instructions` |
| L323 | POST | `/{project_id}/instructions` |
| L357 | GET | `/{project_id}/details` |
| L386 | PATCH | `/{project_id}` |
| L412 | DELETE | `/{project_id}` |
| L440 | DELETE | `/file/{file_id}` |
| L500 | GET | `/file/{file_id}` |
| L526 | POST | `/file/statuses` |
| L553 | POST | `/{project_id}/move_chat_session` |
| L573 | POST | `/remove_chat_session` |
| L592 | GET | `/session/{chat_session_id}/token-count` |
| L620 | GET | `/session/{chat_session_id}/files` |
| L658 | GET | `/{project_id}/token-count` |

### `server/features/tool/api.py`
| Line | Method | Path | Router |
|------|--------|------|--------|
| L82 | POST | `/custom` | admin |
| L105 | PUT | `/custom/{tool_id}` | admin |
| L130 | DELETE | `/custom/{tool_id}` | admin |
| L157 | PATCH | `/status` | admin |
| L206 | POST | `/custom/validate` | admin |
| L219 | GET | `/openapi` | user |
| L236 | GET | `/{tool_id}` | user |
| L249 | GET | `` | user |

### `server/features/user_oauth_token/api.py`
| Line | Method | Path |
|------|--------|------|
| L23 | GET | `/status` |

### `server/features/web_search/api.py`
| Line | Method | Path |
|------|--------|------|
| L220 | POST | `/search` |
| L263 | POST | `/search-lite` |
| L279 | POST | `/open-urls` |

### `server/federated/api.py`
| Line | Method | Path |
|------|--------|------|
| L64 | POST | `` |
| L106 | GET | `/{id}/entities` |
| L148 | GET | `/{id}/credentials/schema` |
| L193 | GET | `/sources/{source}/configuration/schema` |
| L221 | GET | `/sources/{source}/credentials/schema` |
| L252 | POST | `/sources/{source}/credentials/validate` |
| L276 | HEAD | `/{id}/entities/validate` |
| L320 | GET | `/{id}/authorize` |
| L369 | POST | `/callback` |
| L448 | GET | `` |
| L468 | GET | `/oauth-status` |
| L513 | GET | `/{id}` |
| L562 | PUT | `/{id}` |
| L594 | DELETE | `/{id}` |
| L612 | DELETE | `/{id}/oauth` |

### `server/kg/api.py`
| Line | Method | Path | Router |
|------|--------|------|--------|
| L49 | GET | `/exposed` | admin |
| L58 | PUT | `/reset` | admin |
| L71 | GET | `/config` | admin |
| L77 | PUT | `/config` | admin |
| L164 | GET | `/entity-types` | admin |
| L194 | PUT | `/entity-types` | admin |

### `server/manage/administrative.py`
| Line | Method | Path |
|------|--------|------|
| L50 | GET | `/admin/doc-boosts` |
| L76 | POST | `/admin/doc-boosts` |
| L91 | POST | `/admin/doc-hidden` |
| L106 | GET | `/admin/genai-api-key/validate` |
| L138 | POST | `/admin/deletion-attempt` |

### `server/manage/code_interpreter/api.py`
| Line | Method | Path | Router |
|------|--------|------|--------|
| L19 | GET | `/health` | admin |
| L30 | GET | `` | admin |
| L38 | PUT | `` | admin |

### `server/manage/discord_bot/api.py`
| Line | Method | Path |
|------|--------|------|
| L64 | GET | `/config` |
| L81 | POST | `/config` |
| L108 | DELETE | `/config` |
| L132 | DELETE | `/service-api-key` |
| L155 | GET | `/guilds` |
| L165 | POST | `/guilds` |
| L183 | GET | `/guilds/{config_id}` |
| L196 | PATCH | `/guilds/{config_id}` |
| L219 | DELETE | `/guilds/{config_id}` |
| L246 | GET | `/guilds/{config_id}/channels` |
| L265 | PATCH | `/guilds/{guild_config_id}/channels/{channel_config_id}` |

### `server/manage/embedding/api.py`
| Line | Method | Path | Router |
|------|--------|------|--------|
| L34 | POST | `/test-embedding` | admin |
| L66 | GET | `` | admin |
| L75 | GET | `/embedding-provider` | admin |
| L86 | DELETE | `/embedding-provider/{provider_type}` | admin |
| L105 | PUT | `/embedding-provider` | admin |

### `server/manage/opensearch_migration/api.py`
| Line | Method | Path | Router |
|------|--------|------|--------|
| L24 | GET | `/status` | admin |
| L43 | GET | `/retrieval` | admin |
| L54 | PUT | `/retrieval` | admin |

### `server/manage/get_state.py`
| Line | Method | Path |
|------|--------|------|
| L28 | GET | `/health` |
| L33 | GET | `/auth/type` |
| L53 | GET | `/version` |
| L58 | GET | `/versions` |

### `server/manage/image_generation/api.py`
| Line | Method | Path | Router |
|------|--------|------|--------|
| L194 | POST | `/test` | admin |
| L291 | POST | `/config` | admin |
| L354 | GET | `/config` | admin |
| L364 | GET | `/config/{image_provider_id}/credentials` | admin |
| L384 | PUT | `/config/{image_provider_id}` | admin |
| L481 | DELETE | `/config/{image_provider_id}` | admin |
| L512 | POST | `/config/{image_provider_id}/default` | admin |
| L525 | DELETE | `/config/{image_provider_id}/default` | admin |

### `server/manage/llm/api.py`
| Line | Method | Path | Router |
|------|--------|------|--------|
| L214 | GET | `/built-in/options` | admin |
| L221 | GET | `/built-in/options/{provider_name}` | admin |
| L233 | POST | `/test` | admin |
| L292 | POST | `/test/default` | admin |
| L307 | GET | `/provider` | admin |
| L348 | PUT | `/provider` | admin |
| L505 | DELETE | `/provider/{provider_id}` | admin |
| L527 | POST | `/default` | admin |
| L540 | POST | `/default-vision` | admin |
| L553 | GET | `/auto-config` | admin |
| L571 | GET | `/vision-providers` | admin |
| L616 | GET | `/provider` | basic |
| L703 | GET | `/persona/{persona_id}/providers` | basic |
| L802 | GET | `/provider-contextual-cost` | admin |
| L850 | POST | `/bedrock/available-models` | admin |
| L1032 | POST | `/ollama/available-models` | admin |
| L1163 | POST | `/openrouter/available-models` | admin |
| L1251 | POST | `/lm-studio/available-models` | admin |

### `server/manage/search_settings.py`
| Line | Method | Path |
|------|--------|------|
| L46 | POST | `/set-new-search-settings` |
| L147 | POST | `/cancel-new-embedding` |
| L179 | DELETE | `/delete-search-settings` |
| L194 | GET | `/get-current-search-settings` |
| L203 | GET | `/get-secondary-search-settings` |
| L215 | GET | `/get-all-search-settings` |
| L233 | POST | `/update-inference-settings` |
| L264 | GET | `/unstructured-api-key-set` |
| L272 | PUT | `/upsert-unstructured-api-key` |
| L280 | DELETE | `/delete-unstructured-api-key` |

### `server/manage/users.py`
| Line | Method | Path |
|------|--------|------|
| L117 | PATCH | `/manage/set-user-role` |
| L161 | POST | `/manage/users/test-upsert-user` |
| L173 | GET | `/manage/users/accepted` |
| L214 | GET | `/manage/users/invited` |
| L230 | GET | `/manage/users` |
| L332 | GET | `/manage/users/download` |
| L369 | PUT | `/manage/admin/users` |
| L470 | PATCH | `/manage/admin/remove-invited-user` |
| L498 | PATCH | `/manage/admin/deactivate-user` |
| L527 | DELETE | `/manage/admin/delete-user` |
| L571 | PATCH | `/manage/admin/activate-user` |
| L601 | GET | `/manage/admin/valid-domains` |
| L611 | GET | `/users` |
| L626 | GET | `/get-user-role` |
| L724 | GET | `/me` |
| L792 | PATCH | `/temperature-override-enabled` |
| L807 | PATCH | `/shortcut-enabled` |
| L816 | PATCH | `/auto-scroll` |
| L825 | PATCH | `/user/theme-preference` |
| L834 | PATCH | `/user/chat-background` |
| L843 | PATCH | `/user/default-app-mode` |
| L852 | PATCH | `/user/default-model` |
| L861 | PATCH | `/user/personalization` |
| L908 | PATCH | `/user/pinned-assistants` |
| L944 | PATCH | `/user/assistant-list/update/{assistant_id}` |
| L966 | GET | `/user/assistant/preferences` |
| L983 | PATCH | `/user/assistant/{assistant_id}/preferences` |
| L996 | GET | `/user/files/recent` |

### `server/manage/slack_bot.py`
| Line | Method | Path |
|------|--------|------|
| L113 | POST | `/admin/slack-app/channel` |
| L153 | PATCH | `/admin/slack-app/channel/{slack_channel_config_id}` |
| L215 | DELETE | `/admin/slack-app/channel/{slack_channel_config_id}` |
| L228 | GET | `/admin/slack-app/channel` |
| L240 | POST | `/admin/slack-app/bots` |
| L285 | PATCH | `/admin/slack-app/bots/{slack_bot_id}` |
| L307 | DELETE | `/admin/slack-app/bots/{slack_bot_id}` |
| L319 | GET | `/admin/slack-app/bots/{slack_bot_id}` |
| L332 | GET | `/admin/slack-app/bots` |
| L343 | GET | `/admin/slack-app/bots/{bot_id}/config` |

### `server/manage/web_search/api.py`
| Line | Method | Path | Router |
|------|--------|------|--------|
| L58 | GET | `/search-providers` | admin |
| L77 | POST | `/search-providers` | admin |
| L138 | DELETE | `/search-providers/{provider_id}` | admin |
| L150 | POST | `/search-providers/{provider_id}/activate` | admin |
| L170 | POST | `/search-providers/{provider_id}/deactivate` | admin |
| L181 | POST | `/search-providers/test` | admin |
| L231 | GET | `/content-providers` | admin |
| L250 | POST | `/content-providers` | admin |
| L311 | DELETE | `/content-providers/{provider_id}` | admin |
| L323 | POST | `/content-providers/{provider_id}/activate` | admin |
| L343 | POST | `/content-providers/reset-default` | admin |
| L358 | POST | `/content-providers/{provider_id}/deactivate` | admin |
| L369 | POST | `/content-providers/test` | admin |

### `server/onyx_api/ingestion.py`
| Line | Method | Path |
|------|--------|------|
| L44 | GET | `/connector-docs/{cc_pair_id}` |
| L61 | GET | `/ingestion` |
| L77 | POST | `/ingestion` |
| L179 | DELETE | `/ingestion/{document_id}` |

### `server/pat/api.py`
| Line | Method | Path |
|------|--------|------|
| L25 | GET | `` |
| L45 | POST | `` |
| L75 | DELETE | `/{token_id}` |

### `server/query_and_chat/chat_backend.py`
| Line | Method | Path |
|------|--------|------|
| L145 | GET | `/get-user-chat-sessions` |
| L201 | PUT | `/update-chat-session-temperature` |
| L241 | PUT | `/update-chat-session-model` |
| L258 | GET | `/get-chat-session/{session_id}` |
| L371 | POST | `/create-chat-session` |
| L395 | PUT | `/rename-chat-session` |
| L464 | PATCH | `/chat-session/{session_id}` |
| L481 | DELETE | `/delete-all-chat-sessions` |
| L492 | DELETE | `/delete-chat-session/{session_id}` |
| L514 | POST | `/send-chat-message` (supports both `text/event-stream` and `application/json`) |
| L642 | PUT | `/set-message-as-latest` |
| L663 | POST | `/create-chat-message-feedback` |
| L681 | DELETE | `/remove-chat-message-feedback` |
| L700 | GET | `/max-selected-document-tokens` |
| L729 | GET | `/available-context-tokens/{session_id}` |
| L771 | POST | `/seed-chat-session-from-slack` |
| L795 | GET | `/file/{file_id:path}` |
| L831 | GET | `/search` |
| L911 | POST | `/stop-chat-session/{chat_session_id}` |

### `server/query_and_chat/query_backend.py`
| Line | Method | Path | Router |
|------|--------|------|--------|
| L33 | POST | `/search` | admin |
| L77 | GET | `/valid-tags` | basic |

### `server/saml.py`
| Line | Method | Path |
|------|--------|------|
| L193 | GET | `/authorize` |
| L202 | GET | `/callback` |
| L212 | POST | `/callback` |
| L288 | POST | `/logout` |

### `server/settings/api.py`
| Line | Method | Path | Router |
|------|--------|------|--------|
| L38 | PUT | `` | admin |
| L50 | GET | `` | basic |

### `server/token_rate_limits/api.py`
| Line | Method | Path |
|------|--------|------|
| L25 | GET | `/global` |
| L36 | POST | `/global` |
| L55 | PUT | `/rate-limit/{token_rate_limit_id}` |
| L71 | DELETE | `/rate-limit/{token_rate_limit_id}` |

---

## Outbound: LLM Inference (litellm)

| File | Line | Call |
|------|------|------|
| `natural_language_processing/search_nlp_models.py` | L338 | `aembedding(model, input, timeout, api_key, api_base, api_version)` — async embedding call for text vectorisation |

---

## Internal: Periodic Task Schedules (Celery)

| File | Line | Schedule | Description |
|------|------|----------|-------------|
| `background/celery/tasks/beat_schedule.py` | L203 | `crontab(hour=0, minute=0, day_of_week=0)` | Weekly Sunday midnight scheduled beat task |