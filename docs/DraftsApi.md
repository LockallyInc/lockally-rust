# \DraftsApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**approve_draft**](DraftsApi.md#approve_draft) | **POST** /v1/drafts/{draftID}/approve | Approve a pending draft (human)
[**cancel_draft**](DraftsApi.md#cancel_draft) | **POST** /v1/drafts/{draftID}/cancel | Withdraw a pending draft
[**create_conversation_draft**](DraftsApi.md#create_conversation_draft) | **POST** /v1/inboxes/{mailbox}/drafts | Propose a new conversation as a draft
[**create_reply_draft**](DraftsApi.md#create_reply_draft) | **POST** /v1/threads/{threadID}/drafts | Propose a reply as a draft
[**get_draft**](DraftsApi.md#get_draft) | **GET** /v1/drafts/{draftID} | Get a draft
[**list_drafts**](DraftsApi.md#list_drafts) | **GET** /v1/drafts | List drafts
[**reject_draft**](DraftsApi.md#reject_draft) | **POST** /v1/drafts/{draftID}/reject | Reject a pending draft (human)



## approve_draft

> models::DraftResult approve_draft(draft_id)
Approve a pending draft (human)

Sends the draft exactly as reviewed, through the agent stream (loop detector included). Fires draft.approved.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**draft_id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::DraftResult**](DraftResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## cancel_draft

> models::Draft cancel_draft(draft_id)
Withdraw a pending draft

Only the API key that created the draft may cancel it.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**draft_id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::Draft**](Draft.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_conversation_draft

> models::DraftResult create_conversation_draft(mailbox, idempotency_key)
Propose a new conversation as a draft

New-conversation drafts ALWAYS require human approval (policy flag new_thread). Idempotency-Key required.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**mailbox** | **String** |  | [required] |
**idempotency_key** | **String** |  | [required] |

### Return type

[**models::DraftResult**](DraftResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_reply_draft

> models::DraftResult create_reply_draft(thread_id, idempotency_key)
Propose a reply as a draft

The safe default over /reply: the deterministic policy engine auto-sends clean in-thread replies and holds anything risky (PII, new recipients, injection-flagged threads, always-approve mailboxes) for human approval. Fires draft.pending_approval when held. Idempotency-Key required.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**thread_id** | **uuid::Uuid** |  | [required] |
**idempotency_key** | **String** |  | [required] |

### Return type

[**models::DraftResult**](DraftResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_draft

> models::Draft get_draft(draft_id)
Get a draft

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**draft_id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::Draft**](Draft.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_drafts

> models::DraftList list_drafts(status, limit)
List drafts

Filter with ?status=pending_approval|sent|rejected|cancelled. Keys see drafts of granted mailboxes; admin sessions see all.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**status** | Option<**String**> |  |  |
**limit** | Option<**i32**> |  |  |[default to 50]

### Return type

[**models::DraftList**](DraftList.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## reject_draft

> models::Draft reject_draft(draft_id)
Reject a pending draft (human)

Body: {\"reason\": \"...\"} (optional). Fires draft.rejected.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**draft_id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::Draft**](Draft.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

