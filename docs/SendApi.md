# \SendApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**v1_messages_get**](SendApi.md#v1_messages_get) | **GET** /v1/messages | List outbound messages
[**v1_messages_id_delete**](SendApi.md#v1_messages_id_delete) | **DELETE** /v1/messages/{id} | Cancel a scheduled send
[**v1_messages_id_get**](SendApi.md#v1_messages_id_get) | **GET** /v1/messages/{id} | Get message status
[**v1_messages_stats_get**](SendApi.md#v1_messages_stats_get) | **GET** /v1/messages/stats | Aggregate delivery stats
[**v1_send_batch_post**](SendApi.md#v1_send_batch_post) | **POST** /v1/send/batch | Send a batch of emails
[**v1_send_post**](SendApi.md#v1_send_post) | **POST** /v1/send | Send an email



## v1_messages_get

> models::V1MessagesGet200Response v1_messages_get(status, sender, q, since, cursor, limit)
List outbound messages

Returns recent outbound messages for the calling tenant, sorted newest first. Backs the send-status pill in the SvelteKit /sends view and the outbound search box. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**status** | Option<**String**> |  |  |
**sender** | Option<**String**> | Exact match against the `from` mailbox. |  |
**q** | Option<**String**> | Free-text search across subject + sender. |  |
**since** | Option<**chrono::DateTime<chrono::FixedOffset>**> | Only messages queued at or after this RFC 3339 instant. |  |
**cursor** | Option<**String**> | queued_at of the prior page boundary. Pass back the `next_cursor` returned by the previous call. |  |
**limit** | Option<**i32**> |  |  |[default to 50]

### Return type

[**models::V1MessagesGet200Response**](_v1_messages_get_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_messages_id_delete

> v1_messages_id_delete(id)
Cancel a scheduled send

Cancels a still-scheduled message (future queued_at). Already sending/sent → 409.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_messages_id_get

> models::Message v1_messages_id_get(id)
Get message status

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::Message**](Message.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_messages_stats_get

> models::MessageStats v1_messages_stats_get(from, to, domain)
Aggregate delivery stats

Counts by delivery outcome (delivered/bounced/deferred/complaint) plus rates over a window, from the delivery-event store. Privacy-first: this reflects what receiving servers reported, NOT whether a human opened the mail — Lockally does no open/click tracking. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> | Window start (default 7 days ago). |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | Window end (default now). |  |
**domain** | Option<**String**> | Filter by sender domain. |  |

### Return type

[**models::MessageStats**](MessageStats.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_send_batch_post

> models::V1SendBatchPost200Response v1_send_batch_post(idempotency_key, v1_send_batch_post_request)
Send a batch of emails

Sends up to 500 messages in one call. Each is validated and enqueued independently — a bad message fails only its own slot (partial success, HTTP 200). One `Idempotency-Key` header covers the batch; per-message keys are derived as `<key>:<index>`. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**idempotency_key** | **String** |  | [required] |
**v1_send_batch_post_request** | [**V1SendBatchPostRequest**](V1SendBatchPostRequest.md) |  | [required] |

### Return type

[**models::V1SendBatchPost200Response**](_v1_send_batch_post_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_send_post

> models::V1SendPost202Response v1_send_post(idempotency_key, v1_send_post_request)
Send an email

Submits an email for delivery via lockally. Returns 202 immediately once the message is accepted into lockally's queue; the actual SMTP submission to the recipient is async. Track delivery via `GET /v1/messages/{id}` or webhook subscriptions for `delivery.delivered` / `delivery.bounced` / `delivery.complaint`.  **Idempotency-Key required.** Per design L7 — any unique string per send, 24-hour dedupe window. Repeated calls with the same key return byte-exact the original response and do NOT create a duplicate message.  **Sender authorisation.** `from` must be a non-disabled mailbox owned by the calling tenant on a verified domain. Sending from aliases is not yet supported.  **Rate cap.** Per-tenant `rate_cap_per_min` (returned on `/v1/tenant`) is enforced — 429 with `Retry-After: 60` once tripped.  **Recipient warning.** Over 25 total recipients (To+Cc+Bcc) sets a `warning` field in the response — large fan-outs queue noticeably at scale. Hard cap is 100/send. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**idempotency_key** | **String** |  | [required] |
**v1_send_post_request** | [**V1SendPostRequest**](V1SendPostRequest.md) |  | [required] |

### Return type

[**models::V1SendPost202Response**](_v1_send_post_202_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

