# \TenantApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**v1_tenant_get**](TenantApi.md#v1_tenant_get) | **GET** /v1/tenant | Get the calling tenant
[**v1_usage_get**](TenantApi.md#v1_usage_get) | **GET** /v1/usage | Usage snapshot



## v1_tenant_get

> models::Tenant v1_tenant_get()
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


## v1_usage_get

> models::V1UsageGet200Response v1_usage_get()
Usage snapshot

Returns the tenant's current usage + cap consumption. Designed for poll-based alerting on the integrator side (e.g. \"warn when daily quota is 80% used\"). Refreshed live from Postgres — there is no cache, so callers should poll at most once per minute. 

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::V1UsageGet200Response**](_v1_usage_get_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

