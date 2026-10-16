# \ApiKeysApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_api_key**](ApiKeysApi.md#create_api_key) | **POST** /v1/api-keys | Create an API key
[**list_api_keys**](ApiKeysApi.md#list_api_keys) | **GET** /v1/api-keys | List API keys
[**revoke_api_key**](ApiKeysApi.md#revoke_api_key) | **DELETE** /v1/api-keys/{id} | Revoke an API key



## create_api_key

> models::CreateApiKey201Response create_api_key(create_api_key_request)
Create an API key

Provisions a fresh API key for the calling tenant.  **The full `secret` is included in this response ONLY**, store it immediately. The cleartext secret is not recoverable from the argon2id hash kept server-side; rotate by creating a new key and revoking the old one. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**create_api_key_request** | [**CreateApiKeyRequest**](CreateApiKeyRequest.md) |  | [required] |

### Return type

[**models::CreateApiKey201Response**](createApiKey_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_api_keys

> models::ListApiKeys200Response list_api_keys()
List API keys

Returns all API keys (active and revoked) belonging to the calling tenant. The `secret` is **never** returned, only prefix + metadata. 

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::ListApiKeys200Response**](listApiKeys_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## revoke_api_key

> revoke_api_key(id)
Revoke an API key

Soft-deletes (sets `revoked_at`) on the named key. The row stays for audit purposes; the key no longer authenticates.  You **cannot revoke the key currently being used** to make this call, that would lock you out. Use a different `tenant:admin` key. 

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

