# \AddOnsApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**activate_add_on**](AddOnsApi.md#activate_add_on) | **POST** /v1/add-ons/{name}/activate | Activate an add-on
[**cancel_add_on**](AddOnsApi.md#cancel_add_on) | **POST** /v1/add-ons/{name}/cancel | Cancel an add-on
[**get_add_on_status**](AddOnsApi.md#get_add_on_status) | **GET** /v1/add-ons/{name} | Get add-on status
[**list_add_ons**](AddOnsApi.md#list_add_ons) | **GET** /v1/add-ons | List add-ons



## activate_add_on

> models::ActivateAddOn200Response activate_add_on(name)
Activate an add-on

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**name** | **String** | Add-on key | [required] |

### Return type

[**models::ActivateAddOn200Response**](activateAddOn_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## cancel_add_on

> cancel_add_on(name)
Cancel an add-on

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**name** | **String** | Add-on key | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_add_on_status

> models::GetAddOnStatus200Response get_add_on_status(name)
Get add-on status

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**name** | **String** | Add-on key | [required] |

### Return type

[**models::GetAddOnStatus200Response**](getAddOnStatus_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_add_ons

> models::ListAddOns200Response list_add_ons()
List add-ons

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::ListAddOns200Response**](listAddOns_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

