# \AliasesApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**v1_aliases_address_delete**](AliasesApi.md#v1_aliases_address_delete) | **DELETE** /v1/aliases/{address} | Delete an alias
[**v1_aliases_get**](AliasesApi.md#v1_aliases_get) | **GET** /v1/aliases | List aliases
[**v1_aliases_post**](AliasesApi.md#v1_aliases_post) | **POST** /v1/aliases | Create an alias



## v1_aliases_address_delete

> v1_aliases_address_delete(address)
Delete an alias

Hard-delete (no soft-delete window — aliases are cheap to recreate).

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**address** | **String** |  | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_aliases_get

> models::V1AliasesGet200Response v1_aliases_get()
List aliases

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::V1AliasesGet200Response**](_v1_aliases_get_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_aliases_post

> models::Alias v1_aliases_post(v1_aliases_post_request)
Create an alias

Creates an email alias. `alias_address` must be on a verified tenant-owned domain. `alias_target` can be any email — intra-tenant or external (forwarding to a Gmail account is a legitimate use). 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**v1_aliases_post_request** | [**V1AliasesPostRequest**](V1AliasesPostRequest.md) |  | [required] |

### Return type

[**models::Alias**](Alias.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

