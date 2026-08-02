# \WebhooksApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**v1_webhooks_get**](WebhooksApi.md#v1_webhooks_get) | **GET** /v1/webhooks | List webhooks
[**v1_webhooks_id_delete**](WebhooksApi.md#v1_webhooks_id_delete) | **DELETE** /v1/webhooks/{id} | Delete a webhook
[**v1_webhooks_id_patch**](WebhooksApi.md#v1_webhooks_id_patch) | **PATCH** /v1/webhooks/{id} | Update a webhook
[**v1_webhooks_post**](WebhooksApi.md#v1_webhooks_post) | **POST** /v1/webhooks | Create a webhook



## v1_webhooks_get

> models::V1WebhooksGet200Response v1_webhooks_get()
List webhooks

Returns the calling tenant's webhook subscriptions. Never returns the signing secret — only metadata. 

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::V1WebhooksGet200Response**](_v1_webhooks_get_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_webhooks_id_delete

> v1_webhooks_id_delete(id)
Delete a webhook

Hard-delete; cascades to `webhook_deliveries` history.

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


## v1_webhooks_id_patch

> models::Webhook v1_webhooks_id_patch(id, v1_webhooks_id_patch_request)
Update a webhook

Supply at least one of `url`, `events`, `paused`. Setting `paused` to `false` ALSO resets `consecutive_failures` to 0 — re-arms the 50-failure auto-pause counter. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |
**v1_webhooks_id_patch_request** | [**V1WebhooksIdPatchRequest**](V1WebhooksIdPatchRequest.md) |  | [required] |

### Return type

[**models::Webhook**](Webhook.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_webhooks_post

> models::Webhook v1_webhooks_post(v1_webhooks_post_request)
Create a webhook

Subscribes a URL to one or more event types. Returns the `signing_secret` ONCE in the response — store it immediately. The dispatcher signs every outbound POST per design L3:      X-Lockally-Signature: t=<unix>,v1=<hex(hmac_sha256(secret, t + \".\" + body))>  Verify on your end using HMAC-SHA256 with a 5-minute timestamp window (replay protection). A reference verifier ships in [internal/webhook](https://github.com/ucheigwedinma/lockally/blob/main/internal/webhook/sign.go).  Event names: see the [event catalogue](https://github.com/ucheigwedinma/lockally/blob/main/docs/v1-design.md#64-webhook-event-catalogue-v1). 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**v1_webhooks_post_request** | [**V1WebhooksPostRequest**](V1WebhooksPostRequest.md) |  | [required] |

### Return type

[**models::Webhook**](Webhook.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

