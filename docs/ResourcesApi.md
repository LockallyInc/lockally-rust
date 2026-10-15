# \ResourcesApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_resource**](ResourcesApi.md#create_resource) | **POST** /v1/resources | Create a resource
[**delete_resource**](ResourcesApi.md#delete_resource) | **DELETE** /v1/resources/{id} | Delete a resource
[**get_resource**](ResourcesApi.md#get_resource) | **GET** /v1/resources/{id} | Get a resource
[**list_resources**](ResourcesApi.md#list_resources) | **GET** /v1/resources | List resources
[**update_resource**](ResourcesApi.md#update_resource) | **PATCH** /v1/resources/{id} | Update a resource



## create_resource

> models::Resource create_resource(create_resource_request)
Create a resource

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**create_resource_request** | [**CreateResourceRequest**](CreateResourceRequest.md) |  | [required] |

### Return type

[**models::Resource**](Resource.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_resource

> delete_resource(id)
Delete a resource

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


## get_resource

> models::Resource get_resource(id)
Get a resource

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::Resource**](Resource.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_resources

> models::ListResources200Response list_resources()
List resources

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::ListResources200Response**](listResources_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_resource

> models::Resource update_resource(id, update_resource_request)
Update a resource

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |
**update_resource_request** | [**UpdateResourceRequest**](UpdateResourceRequest.md) |  | [required] |

### Return type

[**models::Resource**](Resource.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

