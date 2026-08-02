# \DashboardApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_audit_summary**](DashboardApi.md#get_audit_summary) | **GET** /v1/audit-summary | Audit summary for the dashboard
[**get_domains_status**](DashboardApi.md#get_domains_status) | **GET** /v1/domains/status | Domain health status for the dashboard
[**get_integrations_summary**](DashboardApi.md#get_integrations_summary) | **GET** /v1/integrations-summary | Integrations summary for the dashboard
[**get_security**](DashboardApi.md#get_security) | **GET** /v1/security | Security overview for the dashboard
[**get_storage**](DashboardApi.md#get_storage) | **GET** /v1/storage | Storage usage for the dashboard
[**get_tenant_health**](DashboardApi.md#get_tenant_health) | **GET** /v1/health | Full tenant health report
[**get_user_insights**](DashboardApi.md#get_user_insights) | **GET** /v1/user-insights | User insights for the dashboard



## get_audit_summary

> models::GetAuditSummary200Response get_audit_summary()
Audit summary for the dashboard

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::GetAuditSummary200Response**](getAuditSummary_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_domains_status

> models::GetDomainsStatus200Response get_domains_status()
Domain health status for the dashboard

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::GetDomainsStatus200Response**](getDomainsStatus_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_integrations_summary

> models::GetIntegrationsSummary200Response get_integrations_summary()
Integrations summary for the dashboard

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::GetIntegrationsSummary200Response**](getIntegrationsSummary_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_security

> models::GetSecurity200Response get_security()
Security overview for the dashboard

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::GetSecurity200Response**](getSecurity_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_storage

> models::GetStorage200Response get_storage()
Storage usage for the dashboard

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::GetStorage200Response**](getStorage_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_tenant_health

> serde_json::Value get_tenant_health()
Full tenant health report

### Parameters

This endpoint does not need any parameter.

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_user_insights

> models::GetUserInsights200Response get_user_insights()
User insights for the dashboard

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::GetUserInsights200Response**](getUserInsights_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

