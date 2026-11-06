# \TenantApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_tenant**](TenantApi.md#get_tenant) | **GET** /v1/tenant | Get the calling tenant
[**get_tracking_policy**](TenantApi.md#get_tracking_policy) | **GET** /v1/tracking | Get the engagement tracking policy
[**get_usage**](TenantApi.md#get_usage) | **GET** /v1/usage | Usage snapshot
[**update_tracking_policy**](TenantApi.md#update_tracking_policy) | **PUT** /v1/tracking | Update the engagement tracking policy



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


## get_tracking_policy

> models::TrackingPolicy get_tracking_policy()
Get the engagement tracking policy

Whether open and click tracking are enabled for this account. **Both are off until switched on**, and an account that has never set a policy reads as off rather than as an error.  `configured` reports whether this deployment holds a signing secret. Without one no tracking token can be minted or verified, so tracking cannot work however the flags are set, and a caller seeing `track_opens: true` with nothing arriving deserves to know why. 

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::TrackingPolicy**](TrackingPolicy.md)

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


## update_tracking_policy

> models::TrackingPolicy update_tracking_policy(update_tracking_policy_request)
Update the engagement tracking policy

Enables or disables tracking for the account. Send either flag or both; an omitted flag is left unchanged rather than reset.  **Enabling this changes what Lockally collects about your recipients**, who have no relationship with us. You are the controller for them. What is collected is a user-agent string, a timestamp, and for a click the destination URL: **no IP address**, ever. The change is written to your audit log. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**update_tracking_policy_request** | [**UpdateTrackingPolicyRequest**](UpdateTrackingPolicyRequest.md) |  | [required] |

### Return type

[**models::TrackingPolicy**](TrackingPolicy.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

