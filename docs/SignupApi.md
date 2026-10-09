# \SignupApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**signup**](SignupApi.md#signup) | **POST** /v1/signup | Sign up a new tenant



## signup

> models::V1AdminLoginPost200Response signup(signup_request)
Sign up a new tenant

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**signup_request** | [**SignupRequest**](SignupRequest.md) |  | [required] |

### Return type

[**models::V1AdminLoginPost200Response**](_v1_admin_login_post_200_response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

