# \SuppressionsApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_suppression**](SuppressionsApi.md#create_suppression) | **POST** /v1/suppressions | Add a suppression
[**delete_suppression**](SuppressionsApi.md#delete_suppression) | **DELETE** /v1/suppressions/{email} | Remove a suppression
[**get_suppression**](SuppressionsApi.md#get_suppression) | **GET** /v1/suppressions/{email} | Check whether an address is suppressed
[**list_suppressions**](SuppressionsApi.md#list_suppressions) | **GET** /v1/suppressions | List suppressed recipients



## create_suppression

> models::Suppression create_suppression(create_suppression_request)
Add a suppression

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**create_suppression_request** | [**CreateSuppressionRequest**](CreateSuppressionRequest.md) |  | [required] |

### Return type

[**models::Suppression**](Suppression.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_suppression

> delete_suppression(email)
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


## get_suppression

> models::Suppression get_suppression(email)
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


## list_suppressions

> models::ListSuppressions200Response list_suppressions(reason, cursor, limit)
List suppressed recipients

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**reason** | Option<**String**> |  |  |
**cursor** | Option<**String**> |  |  |
**limit** | Option<**i32**> |  |  |[default to 50]

### Return type

[**models::ListSuppressions200Response**](listSuppressions_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

