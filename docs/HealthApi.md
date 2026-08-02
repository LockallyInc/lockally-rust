# \HealthApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**healthz_get**](HealthApi.md#healthz_get) | **GET** /healthz | Liveness check



## healthz_get

> models::HealthzGet200Response healthz_get()
Liveness check

Returns 200 if the process is up and the database pings cleanly. No authentication required.

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::HealthzGet200Response**](_healthz_get_200_response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

