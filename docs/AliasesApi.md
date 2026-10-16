# \AliasesApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_alias**](AliasesApi.md#create_alias) | **POST** /v1/aliases | Create an alias
[**delete_alias**](AliasesApi.md#delete_alias) | **DELETE** /v1/aliases/{address} | Delete an alias
[**list_aliases**](AliasesApi.md#list_aliases) | **GET** /v1/aliases | List aliases



## create_alias

> models::Alias create_alias(create_alias_request)
Create an alias

Creates an email alias. `alias_address` must be on a verified tenant-owned domain and must not be the address of an existing mailbox (live, suspended or deleted). `alias_target` must be an active mailbox in the same workspace; forwarding to an address Lockally does not host is not supported. The alias delivers as soon as the call returns. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**create_alias_request** | [**CreateAliasRequest**](CreateAliasRequest.md) |  | [required] |

### Return type

[**models::Alias**](Alias.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_alias

> delete_alias(address)
Delete an alias

Hard-delete (no soft-delete window, aliases are cheap to recreate).

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


## list_aliases

> models::ListAliases200Response list_aliases()
List aliases

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::ListAliases200Response**](listAliases_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

