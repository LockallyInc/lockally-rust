# \HealthApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**health_check**](HealthApi.md#health_check) | **GET** /healthz | Liveness check



## health_check

> models::HealthCheck200Response health_check()
Liveness check

Returns 200 if the process is up and the database pings cleanly. No authentication required.

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::HealthCheck200Response**](healthCheck_200_response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

