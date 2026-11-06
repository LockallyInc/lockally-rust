# \SendApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**cancel_message**](SendApi.md#cancel_message) | **DELETE** /v1/messages/{id} | Cancel a scheduled send
[**get_message**](SendApi.md#get_message) | **GET** /v1/messages/{id} | Get message status
[**get_message_stats**](SendApi.md#get_message_stats) | **GET** /v1/messages/stats | Aggregate delivery stats
[**list_messages**](SendApi.md#list_messages) | **GET** /v1/messages | List outbound messages
[**send_email**](SendApi.md#send_email) | **POST** /v1/send | Send an email
[**send_email_batch**](SendApi.md#send_email_batch) | **POST** /v1/send/batch | Send a batch of emails



## cancel_message

> cancel_message(id)
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


## get_message

> models::MessageDetail get_message(id)
Get message status

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::MessageDetail**](MessageDetail.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_message_stats

> models::MessageStats get_message_stats(from, to, domain, tag)
Aggregate delivery stats

Counts by delivery outcome (delivered/bounced/deferred/complaint) plus rates over a window, from the delivery-event store. Privacy-first: this reflects what receiving servers reported, NOT whether a human opened the mail, Lockally does no open/click tracking. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> | Window start (default 7 days ago). |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> | Window end (default now). |  |
**domain** | Option<**String**> | Filter by sender domain. |  |
**tag** | Option<**String**> | Group the window by the sender's own tags: one tag, or a comma-separated set meaning ANY. Case-insensitive. This is the dimension that tells a transactional stream from a notification one. |  |

### Return type

[**models::MessageStats**](MessageStats.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_messages

> models::ListMessages200Response list_messages(status, sender, tag, q, since, cursor, limit, sort, order)
List outbound messages

Returns recent outbound messages for the calling tenant, sorted newest first. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**status** | Option<**String**> |  |  |
**sender** | Option<**String**> | Exact match against the `from` mailbox. |  |
**tag** | Option<**String**> | Filter to messages carrying any of these tags. One tag, or a comma-separated set meaning ANY. Case-insensitive: the value is normalised the same way tags are on write. |  |
**q** | Option<**String**> | Free-text search across subject + sender. |  |
**since** | Option<**chrono::DateTime<chrono::FixedOffset>**> | Only messages queued at or after this RFC 3339 instant. |  |
**cursor** | Option<**String**> | queued_at of the prior page boundary. Pass back the `next_cursor` returned by the previous call. |  |
**limit** | Option<**i32**> |  |  |[default to 50]
**sort** | Option<**String**> | Field to order by. Only indexed columns are offered: an unindexed sort on this table is a full scan of the account's send history. status and sender are filters instead. |  |[default to queued_at]
**order** | Option<**String**> | Defaults to desc for the default field and asc for any other. The order is always made total by a tie-break on id, so paging cannot repeat or skip a row that shares a timestamp. cursor encodes queued_at, so combining it with another sort is a 400 rather than a wrong page. |  |

### Return type

[**models::ListMessages200Response**](listMessages_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## send_email

> models::SendEmail200Response send_email(idempotency_key, send_email_request)
Send an email

Submits an email for delivery via lockally. Returns 202 immediately once the message is accepted into lockally's queue; the actual SMTP submission to the recipient is async. Track delivery via `GET /v1/messages/{id}` or webhook subscriptions for `delivery.delivered` / `delivery.bounced` / `delivery.complaint`.  **Idempotency-Key required.** Any unique string per send, 24-hour dedupe window. Repeated calls with the same key return byte-exact the original response and do NOT create a duplicate message.  **Sender authorisation.** `from` must be an address the calling tenant owns on a verified domain. A mailbox always qualifies. On business and combined accounts an **alias** qualifies too, so a send-only address such as `no-reply@` need not be a billed seat. An alias on an unverified domain, or one belonging to another account, is refused with `403`. A catch-all creates no aliases and so grants no sending rights.  **Rate cap.** Per-tenant `rate_cap_per_min` (returned on `/v1/tenant`) is enforced, 429 with `Retry-After: 60` once tripped.  **Recipient warning.** Over 25 total recipients (To+Cc+Bcc) sets a `warning` field in the response, large fan-outs queue noticeably at scale. Hard cap is 100/send.  **Not every success is a 202.** Check the status code, not just the body. A `200` means nothing was queued: either every recipient was already suppressed, or the call used a test key and the send was simulated. Both are successes, and neither produces a real delivery. See the `200` response below.  **Warm-up headers.** While the platform is in its outbound warm-up ramp, accepted sends carry `X-Warmup-Day`, `X-Warmup-Daily-Cap` and `X-Warmup-Used-Today`. They describe a platform-wide cap shared by every tenant, not your own allowance, and they disappear once the ramp finishes. Hitting the cap returns 429. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**idempotency_key** | **String** |  | [required] |
**send_email_request** | [**SendEmailRequest**](SendEmailRequest.md) |  | [required] |

### Return type

[**models::SendEmail200Response**](sendEmail_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## send_email_batch

> models::SendEmailBatch200Response send_email_batch(idempotency_key, send_email_batch_request)
Send a batch of emails

Sends up to 500 messages in one call. Each is validated and enqueued independently, a bad message fails only its own slot (partial success, HTTP 200). One `Idempotency-Key` header covers the batch; per-message keys are derived as `<key>:<index>`. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**idempotency_key** | **String** |  | [required] |
**send_email_batch_request** | [**SendEmailBatchRequest**](SendEmailBatchRequest.md) |  | [required] |

### Return type

[**models::SendEmailBatch200Response**](sendEmailBatch_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

