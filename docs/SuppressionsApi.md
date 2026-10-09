# \SuppressionsApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**v1_suppressions_email_delete**](SuppressionsApi.md#v1_suppressions_email_delete) | **DELETE** /v1/suppressions/{email} | Remove a suppression
[**v1_suppressions_email_get**](SuppressionsApi.md#v1_suppressions_email_get) | **GET** /v1/suppressions/{email} | Check whether an address is suppressed
[**v1_suppressions_get**](SuppressionsApi.md#v1_suppressions_get) | **GET** /v1/suppressions | List suppressed recipients
[**v1_suppressions_post**](SuppressionsApi.md#v1_suppressions_post) | **POST** /v1/suppressions | Add a suppression



## v1_suppressions_email_delete

> v1_suppressions_email_delete(email)
Remove a suppression

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**email** | **String** |  | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_suppressions_email_get

> models::Suppression v1_suppressions_email_get(email)
Check whether an address is suppressed

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**email** | **String** |  | [required] |

### Return type

[**models::Suppression**](Suppression.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_suppressions_get

> models::V1SuppressionsGet200Response v1_suppressions_get(reason, cursor, limit)
List suppressed recipients

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**reason** | Option<**String**> |  |  |
**cursor** | Option<**String**> |  |  |
**limit** | Option<**i32**> |  |  |[default to 50]

### Return type

[**models::V1SuppressionsGet200Response**](_v1_suppressions_get_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_suppressions_post

> models::Suppression v1_suppressions_post(v1_suppressions_post_request)
Add a suppression

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**v1_suppressions_post_request** | [**V1SuppressionsPostRequest**](V1SuppressionsPostRequest.md) |  | [required] |

### Return type

[**models::Suppression**](Suppression.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

