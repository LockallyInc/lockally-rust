# \WebhooksApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_webhook**](WebhooksApi.md#create_webhook) | **POST** /v1/webhooks | Create a webhook
[**delete_webhook**](WebhooksApi.md#delete_webhook) | **DELETE** /v1/webhooks/{id} | Delete a webhook
[**list_webhooks**](WebhooksApi.md#list_webhooks) | **GET** /v1/webhooks | List webhooks
[**update_webhook**](WebhooksApi.md#update_webhook) | **PATCH** /v1/webhooks/{id} | Update a webhook



## create_webhook

> models::Webhook create_webhook(create_webhook_request)
Create a webhook

Subscribes a URL to one or more event types. Returns the `signing_secret` ONCE in the response — store it immediately. The dispatcher signs every outbound POST per design L3:      X-Lockally-Signature: t=<unix>,v1=<hex(hmac_sha256(secret, t + \".\" + body))>  Verify on your end using HMAC-SHA256 with a 5-minute timestamp window (replay protection). A reference verifier ships in [internal/webhook](https://github.com/ucheigwedinma/lockally/blob/main/internal/webhook/sign.go).  Event names: see the [event catalogue](https://github.com/ucheigwedinma/lockally/blob/main/docs/v1-design.md#64-webhook-event-catalogue-v1). 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**create_webhook_request** | [**CreateWebhookRequest**](CreateWebhookRequest.md) |  | [required] |

### Return type

[**models::Webhook**](Webhook.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_webhook

> delete_webhook(id)
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


## list_webhooks

> models::ListWebhooks200Response list_webhooks()
List webhooks

Returns the calling tenant's webhook subscriptions. Never returns the signing secret — only metadata. 

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::ListWebhooks200Response**](listWebhooks_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_webhook

> models::Webhook update_webhook(id, update_webhook_request)
Update a webhook

Supply at least one of `url`, `events`, `paused`. Setting `paused` to `false` ALSO resets `consecutive_failures` to 0 — re-arms the 50-failure auto-pause counter. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |
**update_webhook_request** | [**UpdateWebhookRequest**](UpdateWebhookRequest.md) |  | [required] |

### Return type

[**models::Webhook**](Webhook.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

