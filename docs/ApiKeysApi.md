# \ApiKeysApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**v1_api_keys_get**](ApiKeysApi.md#v1_api_keys_get) | **GET** /v1/api-keys | List API keys
[**v1_api_keys_id_delete**](ApiKeysApi.md#v1_api_keys_id_delete) | **DELETE** /v1/api-keys/{id} | Revoke an API key
[**v1_api_keys_post**](ApiKeysApi.md#v1_api_keys_post) | **POST** /v1/api-keys | Create an API key



## v1_api_keys_get

> models::V1ApiKeysGet200Response v1_api_keys_get()
List API keys

Returns all API keys (active and revoked) belonging to the calling tenant. The `secret` is **never** returned — only prefix + metadata. 

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::V1ApiKeysGet200Response**](_v1_api_keys_get_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_api_keys_id_delete

> v1_api_keys_id_delete(id)
Revoke an API key

Soft-deletes (sets `revoked_at`) on the named key. The row stays for audit purposes; the key no longer authenticates.  You **cannot revoke the key currently being used** to make this call — that would lock you out. Use a different `tenant:admin` key. 

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


## v1_api_keys_post

> models::V1ApiKeysPost201Response v1_api_keys_post(v1_api_keys_post_request)
Create an API key

Provisions a fresh API key for the calling tenant.  **The full `secret` is included in this response ONLY** — store it immediately. The cleartext secret is not recoverable from the argon2id hash kept server-side; rotate by creating a new key and revoking the old one. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**v1_api_keys_post_request** | [**V1ApiKeysPostRequest**](V1ApiKeysPostRequest.md) |  | [required] |

### Return type

[**models::V1ApiKeysPost201Response**](_v1_api_keys_post_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

