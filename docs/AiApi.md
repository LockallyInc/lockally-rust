# \AiApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**classify_thread**](AiApi.md#classify_thread) | **POST** /v1/threads/{threadID}/classify | LLM-classify a thread
[**create_ai_units_checkout**](AiApi.md#create_ai_units_checkout) | **POST** /v1/billing/ai-units/checkout | Buy prepaid AI units
[**get_ai_config**](AiApi.md#get_ai_config) | **GET** /v1/ai-config | Read the tenant's AI configuration
[**update_ai_config**](AiApi.md#update_ai_config) | **PUT** /v1/ai-config | Configure the AI tier



## classify_thread

> models::ThreadClassification classify_thread(thread_id, refresh)
LLM-classify a thread

Returns {intent, urgency, summary, suggested_action} via the tenant's AI tier (BYOK or prepaid units, see /v1/ai-config). Cached per thread state: unchanged threads return the cache free; ?refresh=true forces a re-run. A failed model call charges nothing. 402 when the AI tier is off.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**thread_id** | **uuid::Uuid** |  | [required] |
**refresh** | Option<**bool**> |  |  |

### Return type

[**models::ThreadClassification**](ThreadClassification.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_ai_units_checkout

> models::CreateAiUnitsCheckout200Response create_ai_units_checkout()
Buy prepaid AI units

Body: {\"bundle\": \"100|500|2000\"}. One classification = one unit; bundles expire after 6 months. Admin session required. 503 until Paystack billing is configured.

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::CreateAiUnitsCheckout200Response**](createAiUnitsCheckout_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_ai_config

> models::AiConfig get_ai_config()
Read the tenant's AI configuration

Mode (off/byok/units), model, masked key hint, AI-unit balance, whether the units tier is available on this deployment.

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::AiConfig**](AiConfig.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_ai_config

> models::AiConfigUpdate update_ai_config()
Configure the AI tier

Body: {\"mode\": \"off|byok|units\", \"model\": \"...\", \"anthropic_key\": \"sk-ant-...\"}. BYOK keys are stored AES-256-GCM encrypted; the cleartext is never returned. Omit anthropic_key to keep the stored one.

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::AiConfigUpdate**](AiConfigUpdate.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

