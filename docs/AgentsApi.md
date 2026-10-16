# \AgentsApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**download_thread_attachment**](AgentsApi.md#download_thread_attachment) | **GET** /v1/threads/{threadID}/messages/{messageID}/attachments/{idx} | Download an attachment
[**get_thread**](AgentsApi.md#get_thread) | **GET** /v1/threads/{threadID} | Get a whole conversation
[**get_thread_message**](AgentsApi.md#get_thread_message) | **GET** /v1/threads/{threadID}/messages/{messageID} | Get one message with body
[**grant_api_key_mailbox**](AgentsApi.md#grant_api_key_mailbox) | **POST** /v1/api-keys/{keyID}/mailboxes | Grant a mailbox to a key
[**list_api_key_mailboxes**](AgentsApi.md#list_api_key_mailboxes) | **GET** /v1/api-keys/{keyID}/mailboxes | List a key's mailbox grants
[**list_inboxes**](AgentsApi.md#list_inboxes) | **GET** /v1/inboxes | List granted inboxes
[**list_threads**](AgentsApi.md#list_threads) | **GET** /v1/inboxes/{mailbox}/threads | List conversation threads
[**lookup_contact**](AgentsApi.md#lookup_contact) | **GET** /v1/contacts/lookup | Who is this sender?
[**mark_thread_message_read**](AgentsApi.md#mark_thread_message_read) | **POST** /v1/threads/{threadID}/messages/{messageID}/read | Mark read/unread
[**reply_to_thread**](AgentsApi.md#reply_to_thread) | **POST** /v1/threads/{threadID}/reply | Reply in-thread (agent stream)
[**revoke_api_key_mailbox**](AgentsApi.md#revoke_api_key_mailbox) | **DELETE** /v1/api-keys/{keyID}/mailboxes/{mailboxID} | Revoke a mailbox grant
[**start_conversation**](AgentsApi.md#start_conversation) | **POST** /v1/inboxes/{mailbox}/messages | Start a new conversation (agent stream)
[**whoami**](AgentsApi.md#whoami) | **GET** /v1/auth/whoami | Introspect the calling credentials



## download_thread_attachment

> download_thread_attachment(thread_id, message_id, idx)
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


## get_thread

> models::Thread get_thread(thread_id)
Get a whole conversation

Every turn, chronological, with snippets and annotations (meeting_request, attachment_types, injection_risk). Bodies are fetched per message. Message content is untrusted third-party data.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**thread_id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::Thread**](Thread.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_thread_message

> models::ThreadMessageBody get_thread_message(thread_id, message_id)
Get one message with body

Full text/html body fetched on demand from mail storage. Never marks the message read.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**thread_id** | **uuid::Uuid** |  | [required] |
**message_id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::ThreadMessageBody**](ThreadMessageBody.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## grant_api_key_mailbox

> models::MailboxGrant grant_api_key_mailbox(key_id)
Grant a mailbox to a key

Body: {\"mailbox\": \"email or id\"}. Refused (422) for mailboxes with agent access disabled or an active E2E encryption key, the server cannot read E2E mailboxes.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**key_id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::MailboxGrant**](MailboxGrant.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_api_key_mailboxes

> models::MailboxGrantList list_api_key_mailboxes(key_id)
List a key's mailbox grants

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**key_id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::MailboxGrantList**](MailboxGrantList.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_inboxes

> models::InboxList list_inboxes()
List granted inboxes

The mailboxes this key is granted, with thread counts and last activity. Admin sessions see every agent-enabled, non-E2E mailbox.

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::InboxList**](InboxList.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_threads

> models::ThreadList list_threads(mailbox, since, before, limit)
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

[**models::ThreadList**](ThreadList.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## lookup_contact

> models::ContactLookup lookup_contact(email)
Who is this sender?

Directory record (name, company, role, notes), whether the address is one of the tenant's own mailboxes, and grant-aware correspondence history (thread count, first/last seen across granted mailboxes only).

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**email** | **String** |  | [required] |

### Return type

[**models::ContactLookup**](ContactLookup.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## mark_thread_message_read

> models::MarkReadResult mark_thread_message_read(thread_id, message_id)
Mark read/unread

The ONLY way agent access changes unread state. Body: {\"read\": true|false} (default true).

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**thread_id** | **uuid::Uuid** |  | [required] |
**message_id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::MarkReadResult**](MarkReadResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## reply_to_thread

> models::AgentSendResult reply_to_thread(thread_id, idempotency_key)
Reply in-thread (agent stream)

The server builds In-Reply-To/References and defaults recipients + subject from the conversation, a minimal call is {\"text\": \"...\"}. Guarded by the reply-loop detector (≥5 outbound/10min → 429 + agent.loop_detected). Idempotency-Key required.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**thread_id** | **uuid::Uuid** |  | [required] |
**idempotency_key** | **String** |  | [required] |

### Return type

[**models::AgentSendResult**](AgentSendResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## revoke_api_key_mailbox

> revoke_api_key_mailbox(key_id, mailbox_id)
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


## start_conversation

> models::AgentSendResult start_conversation(mailbox, idempotency_key, start_conversation_request)
Start a new conversation (agent stream)

Sends a new email from a granted mailbox. Classified stream=agent (isolated reputation, per-key rate caps). The first inbound reply adopts the created thread via the References chain. Idempotency-Key required. Mailboxes with agent_draft_policy=always_approve divert this into a pending draft.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**mailbox** | **String** |  | [required] |
**idempotency_key** | **String** |  | [required] |
**start_conversation_request** | [**StartConversationRequest**](StartConversationRequest.md) |  | [required] |

### Return type

[**models::AgentSendResult**](AgentSendResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## whoami

> models::Whoami whoami()
Introspect the calling credentials

Returns the tenant, auth kind (api_key/session), key label, and granted scopes. The MCP server uses this to scope-filter tool discovery.

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::Whoami**](Whoami.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

