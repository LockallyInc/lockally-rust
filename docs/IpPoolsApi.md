# \IpPoolsApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_dedicated_ip_request**](IpPoolsApi.md#create_dedicated_ip_request) | **POST** /v1/dedicated-ip-requests | Request a dedicated IP
[**get_ip_assignment**](IpPoolsApi.md#get_ip_assignment) | **GET** /v1/ip-assignment | Get current IP assignment
[**list_dedicated_ip_requests**](IpPoolsApi.md#list_dedicated_ip_requests) | **GET** /v1/dedicated-ip-requests | List dedicated IP requests



## create_dedicated_ip_request

> models::DedicatedIpRequest create_dedicated_ip_request(create_dedicated_ip_request_request)
Request a dedicated IP

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**create_dedicated_ip_request_request** | [**CreateDedicatedIpRequestRequest**](CreateDedicatedIpRequestRequest.md) |  | [required] |

### Return type

[**models::DedicatedIpRequest**](DedicatedIPRequest.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_ip_assignment

> models::GetIpAssignment200Response get_ip_assignment()
Get current IP assignment

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::GetIpAssignment200Response**](getIPAssignment_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_dedicated_ip_requests

> models::ListDedicatedIpRequests200Response list_dedicated_ip_requests()
List dedicated IP requests

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::ListDedicatedIpRequests200Response**](listDedicatedIPRequests_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

