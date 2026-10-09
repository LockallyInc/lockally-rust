# \DraftsApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**v1_drafts_draft_id_approve_post**](DraftsApi.md#v1_drafts_draft_id_approve_post) | **POST** /v1/drafts/{draftID}/approve | Approve a pending draft (human)
[**v1_drafts_draft_id_cancel_post**](DraftsApi.md#v1_drafts_draft_id_cancel_post) | **POST** /v1/drafts/{draftID}/cancel | Withdraw a pending draft
[**v1_drafts_draft_id_get**](DraftsApi.md#v1_drafts_draft_id_get) | **GET** /v1/drafts/{draftID} | Get a draft
[**v1_drafts_draft_id_reject_post**](DraftsApi.md#v1_drafts_draft_id_reject_post) | **POST** /v1/drafts/{draftID}/reject | Reject a pending draft (human)
[**v1_drafts_get**](DraftsApi.md#v1_drafts_get) | **GET** /v1/drafts | List drafts
[**v1_inboxes_mailbox_drafts_post**](DraftsApi.md#v1_inboxes_mailbox_drafts_post) | **POST** /v1/inboxes/{mailbox}/drafts | Propose a new conversation as a draft
[**v1_threads_thread_id_drafts_post**](DraftsApi.md#v1_threads_thread_id_drafts_post) | **POST** /v1/threads/{threadID}/drafts | Propose a reply as a draft



## v1_drafts_draft_id_approve_post

> serde_json::Value v1_drafts_draft_id_approve_post(draft_id)
Approve a pending draft (human)

Sends the draft exactly as reviewed, through the agent stream (loop detector included). Fires draft.approved.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**draft_id** | **uuid::Uuid** |  | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_drafts_draft_id_cancel_post

> serde_json::Value v1_drafts_draft_id_cancel_post(draft_id)
Withdraw a pending draft

Only the API key that created the draft may cancel it.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**draft_id** | **uuid::Uuid** |  | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_drafts_draft_id_get

> serde_json::Value v1_drafts_draft_id_get(draft_id)
Get a draft

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**draft_id** | **uuid::Uuid** |  | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_drafts_draft_id_reject_post

> serde_json::Value v1_drafts_draft_id_reject_post(draft_id)
Reject a pending draft (human)

Body: {\"reason\": \"...\"} (optional). Fires draft.rejected.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**draft_id** | **uuid::Uuid** |  | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_drafts_get

> serde_json::Value v1_drafts_get(status, limit)
List drafts

Filter with ?status=pending_approval|sent|rejected|cancelled. Keys see drafts of granted mailboxes; admin sessions see all.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**status** | Option<**String**> |  |  |
**limit** | Option<**i32**> |  |  |[default to 50]

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_inboxes_mailbox_drafts_post

> serde_json::Value v1_inboxes_mailbox_drafts_post(mailbox, idempotency_key)
Propose a new conversation as a draft

New-conversation drafts ALWAYS require human approval (policy flag new_thread). Idempotency-Key required.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**mailbox** | **String** |  | [required] |
**idempotency_key** | **String** |  | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_threads_thread_id_drafts_post

> serde_json::Value v1_threads_thread_id_drafts_post(thread_id, idempotency_key)
Propose a reply as a draft

The safe default over /reply: the deterministic policy engine auto-sends clean in-thread replies and holds anything risky (PII, new recipients, injection-flagged threads, always-approve mailboxes) for human approval. Fires draft.pending_approval when held. Idempotency-Key required.

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

