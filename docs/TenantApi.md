# \TenantApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_tenant**](TenantApi.md#get_tenant) | **GET** /v1/tenant | Get the calling tenant
[**get_usage**](TenantApi.md#get_usage) | **GET** /v1/usage | Usage snapshot



## get_tenant

> models::Tenant get_tenant()
Get the calling tenant

Returns the tenant the presented API key belongs to.

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::Tenant**](Tenant.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_usage

> models::GetUsage200Response get_usage()
Usage snapshot

Returns the tenant's current usage + cap consumption. Designed for poll-based alerting on the integrator side (e.g. \"warn when daily quota is 80% used\"). Computed live on request, so there is no cache, so callers should poll at most once per minute. 

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::GetUsage200Response**](getUsage_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

