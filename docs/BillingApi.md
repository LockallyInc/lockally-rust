# \BillingApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_billing_checkout**](BillingApi.md#create_billing_checkout) | **POST** /v1/billing/checkout | Create a plan checkout session
[**create_units_checkout**](BillingApi.md#create_units_checkout) | **POST** /v1/billing/units/checkout | Create a send-units checkout session
[**get_billing**](BillingApi.md#get_billing) | **GET** /v1/billing | Get billing status



## create_billing_checkout

> models::CreateBillingCheckout200Response create_billing_checkout(create_billing_checkout_request)
Create a plan checkout session

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**create_billing_checkout_request** | [**CreateBillingCheckoutRequest**](CreateBillingCheckoutRequest.md) |  | [required] |

### Return type

[**models::CreateBillingCheckout200Response**](createBillingCheckout_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_units_checkout

> models::CreateUnitsCheckout200Response create_units_checkout(create_units_checkout_request)
Create a send-units checkout session

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**create_units_checkout_request** | [**CreateUnitsCheckoutRequest**](CreateUnitsCheckoutRequest.md) |  | [required] |

### Return type

[**models::CreateUnitsCheckout200Response**](createUnitsCheckout_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_billing

> models::BillingStatus get_billing()
Get billing status

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::BillingStatus**](BillingStatus.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

