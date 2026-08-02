# \DirectoryApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_directory_activity**](DirectoryApi.md#get_directory_activity) | **GET** /v1/directory-activity | Get recent directory activity
[**get_directory_permissions**](DirectoryApi.md#get_directory_permissions) | **GET** /v1/directory-permissions | Get directory permission settings
[**get_directory_stats**](DirectoryApi.md#get_directory_stats) | **GET** /v1/directory-stats | Get directory statistics
[**get_gal_settings**](DirectoryApi.md#get_gal_settings) | **GET** /v1/gal-settings | Get Global Address List settings
[**rebuild_gal_index**](DirectoryApi.md#rebuild_gal_index) | **POST** /v1/gal-settings/rebuild-index | Rebuild the GAL search index
[**sync_gal**](DirectoryApi.md#sync_gal) | **POST** /v1/gal-settings/sync | Sync GAL with external directory sources
[**update_directory_permissions**](DirectoryApi.md#update_directory_permissions) | **PATCH** /v1/directory-permissions | Update directory permission settings
[**update_gal_settings**](DirectoryApi.md#update_gal_settings) | **PATCH** /v1/gal-settings | Update GAL settings



## get_directory_activity

> models::GetDirectoryActivity200Response get_directory_activity()
Get recent directory activity

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::GetDirectoryActivity200Response**](getDirectoryActivity_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_directory_permissions

> models::DirectoryPermissions get_directory_permissions()
Get directory permission settings

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::DirectoryPermissions**](DirectoryPermissions.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_directory_stats

> models::GetDirectoryStats200Response get_directory_stats()
Get directory statistics

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::GetDirectoryStats200Response**](getDirectoryStats_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_gal_settings

> models::GalSettings get_gal_settings()
Get Global Address List settings

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::GalSettings**](GALSettings.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## rebuild_gal_index

> models::GalSettings rebuild_gal_index()
Rebuild the GAL search index

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::GalSettings**](GALSettings.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## sync_gal

> models::GalSettings sync_gal()
Sync GAL with external directory sources

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::GalSettings**](GALSettings.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_directory_permissions

> models::DirectoryPermissions update_directory_permissions(update_directory_permissions_request)
Update directory permission settings

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**update_directory_permissions_request** | [**UpdateDirectoryPermissionsRequest**](UpdateDirectoryPermissionsRequest.md) |  | [required] |

### Return type

[**models::DirectoryPermissions**](DirectoryPermissions.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_gal_settings

> models::GalSettings update_gal_settings(update_gal_settings_request)
Update GAL settings

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**update_gal_settings_request** | [**UpdateGalSettingsRequest**](UpdateGalSettingsRequest.md) |  | [required] |

### Return type

[**models::GalSettings**](GALSettings.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

