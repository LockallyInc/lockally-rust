# \AgentsApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**v1_api_keys_key_id_mailboxes_get**](AgentsApi.md#v1_api_keys_key_id_mailboxes_get) | **GET** /v1/api-keys/{keyID}/mailboxes | List a key's mailbox grants
[**v1_api_keys_key_id_mailboxes_mailbox_id_delete**](AgentsApi.md#v1_api_keys_key_id_mailboxes_mailbox_id_delete) | **DELETE** /v1/api-keys/{keyID}/mailboxes/{mailboxID} | Revoke a mailbox grant
[**v1_api_keys_key_id_mailboxes_post**](AgentsApi.md#v1_api_keys_key_id_mailboxes_post) | **POST** /v1/api-keys/{keyID}/mailboxes | Grant a mailbox to a key
[**v1_auth_whoami_get**](AgentsApi.md#v1_auth_whoami_get) | **GET** /v1/auth/whoami | Introspect the calling credentials
[**v1_contacts_lookup_get**](AgentsApi.md#v1_contacts_lookup_get) | **GET** /v1/contacts/lookup | Who is this sender?
[**v1_inboxes_get**](AgentsApi.md#v1_inboxes_get) | **GET** /v1/inboxes | List granted inboxes
[**v1_inboxes_mailbox_messages_post**](AgentsApi.md#v1_inboxes_mailbox_messages_post) | **POST** /v1/inboxes/{mailbox}/messages | Start a new conversation (agent stream)
[**v1_inboxes_mailbox_threads_get**](AgentsApi.md#v1_inboxes_mailbox_threads_get) | **GET** /v1/inboxes/{mailbox}/threads | List conversation threads
[**v1_threads_thread_id_get**](AgentsApi.md#v1_threads_thread_id_get) | **GET** /v1/threads/{threadID} | Get a whole conversation
[**v1_threads_thread_id_messages_message_id_attachments_idx_get**](AgentsApi.md#v1_threads_thread_id_messages_message_id_attachments_idx_get) | **GET** /v1/threads/{threadID}/messages/{messageID}/attachments/{idx} | Download an attachment
[**v1_threads_thread_id_messages_message_id_get**](AgentsApi.md#v1_threads_thread_id_messages_message_id_get) | **GET** /v1/threads/{threadID}/messages/{messageID} | Get one message with body
[**v1_threads_thread_id_messages_message_id_read_post**](AgentsApi.md#v1_threads_thread_id_messages_message_id_read_post) | **POST** /v1/threads/{threadID}/messages/{messageID}/read | Mark read/unread
[**v1_threads_thread_id_reply_post**](AgentsApi.md#v1_threads_thread_id_reply_post) | **POST** /v1/threads/{threadID}/reply | Reply in-thread (agent stream)



## v1_api_keys_key_id_mailboxes_get

> serde_json::Value v1_api_keys_key_id_mailboxes_get(key_id)
List a key's mailbox grants

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**key_id** | **uuid::Uuid** |  | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_api_keys_key_id_mailboxes_mailbox_id_delete

> v1_api_keys_key_id_mailboxes_mailbox_id_delete(key_id, mailbox_id)
Revoke a mailbox grant

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**key_id** | **uuid::Uuid** |  | [required] |
**mailbox_id** | **uuid::Uuid** |  | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_api_keys_key_id_mailboxes_post

> serde_json::Value v1_api_keys_key_id_mailboxes_post(key_id)
Grant a mailbox to a key

Body: {\"mailbox\": \"email or id\"}. Refused (422) for mailboxes with agent access disabled or an active E2E encryption key — the server cannot read E2E mailboxes.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**key_id** | **uuid::Uuid** |  | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_auth_whoami_get

> serde_json::Value v1_auth_whoami_get()
Introspect the calling credentials

Returns the tenant, auth kind (api_key/session), key label, and granted scopes. The MCP server uses this to scope-filter tool discovery.

### Parameters

This endpoint does not need any parameter.

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_contacts_lookup_get

> serde_json::Value v1_contacts_lookup_get(email)
Who is this sender?

Directory record (name, company, role, notes), whether the address is one of the tenant's own mailboxes, and grant-aware correspondence history (thread count, first/last seen across granted mailboxes only).

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**email** | **String** |  | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_inboxes_get

> serde_json::Value v1_inboxes_get()
List granted inboxes

The mailboxes this key is granted, with thread counts and last activity. Admin sessions see every agent-enabled, non-E2E mailbox.

### Parameters

This endpoint does not need any parameter.

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_inboxes_mailbox_messages_post

> serde_json::Value v1_inboxes_mailbox_messages_post(mailbox, idempotency_key, v1_inboxes_mailbox_messages_post_request)
Start a new conversation (agent stream)

Sends a new email from a granted mailbox. Classified stream=agent (isolated reputation, per-key rate caps). The first inbound reply adopts the created thread via the References chain. Idempotency-Key required. Mailboxes with agent_draft_policy=always_approve divert this into a pending draft.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**mailbox** | **String** |  | [required] |
**idempotency_key** | **String** |  | [required] |
**v1_inboxes_mailbox_messages_post_request** | [**V1InboxesMailboxMessagesPostRequest**](V1InboxesMailboxMessagesPostRequest.md) |  | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_inboxes_mailbox_threads_get

> serde_json::Value v1_inboxes_mailbox_threads_get(mailbox, since, before, limit)
List conversation threads

Newest-active first. Cursors: `?before=<RFC3339>` pages backwards; `?since=<RFC3339>` delta-syncs forward (oldest first) so an agent can catch up in order.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**mailbox** | **String** | mailbox email or id | [required] |
**since** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  |  |
**before** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  |  |
**limit** | Option<**i32**> |  |  |[default to 50]

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_threads_thread_id_get

> serde_json::Value v1_threads_thread_id_get(thread_id)
Get a whole conversation

Every turn, chronological, with snippets and annotations (meeting_request, attachment_types, injection_risk). Bodies are fetched per message. Message content is untrusted third-party data.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**thread_id** | **uuid::Uuid** |  | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_threads_thread_id_messages_message_id_attachments_idx_get

> v1_threads_thread_id_messages_message_id_attachments_idx_get(thread_id, message_id, idx)
Download an attachment

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**thread_id** | **uuid::Uuid** |  | [required] |
**message_id** | **uuid::Uuid** |  | [required] |
**idx** | **u32** |  | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_threads_thread_id_messages_message_id_get

> serde_json::Value v1_threads_thread_id_messages_message_id_get(thread_id, message_id)
Get one message with body

Full text/html body fetched on demand from mail storage. Never marks the message read.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**thread_id** | **uuid::Uuid** |  | [required] |
**message_id** | **uuid::Uuid** |  | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_threads_thread_id_messages_message_id_read_post

> serde_json::Value v1_threads_thread_id_messages_message_id_read_post(thread_id, message_id)
Mark read/unread

The ONLY way agent access changes unread state. Body: {\"read\": true|false} (default true).

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**thread_id** | **uuid::Uuid** |  | [required] |
**message_id** | **uuid::Uuid** |  | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_threads_thread_id_reply_post

> serde_json::Value v1_threads_thread_id_reply_post(thread_id, idempotency_key)
Reply in-thread (agent stream)

The server builds In-Reply-To/References and defaults recipients + subject from the conversation — a minimal call is {\"text\": \"...\"}. Guarded by the reply-loop detector (≥5 outbound/10min → 429 + agent.loop_detected). Idempotency-Key required.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**thread_id** | **uuid::Uuid** |  | [required] |
**idempotency_key** | **String** |  | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

