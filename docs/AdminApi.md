# \AdminApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**v1_admin_login_post**](AdminApi.md#v1_admin_login_post) | **POST** /v1/admin/login | Tenant-admin email+password login
[**v1_admin_logout_post**](AdminApi.md#v1_admin_logout_post) | **POST** /v1/admin/logout | Invalidate the current admin session
[**v1_admin_me_get**](AdminApi.md#v1_admin_me_get) | **GET** /v1/admin/me | Get the current admin + tenant



## v1_admin_login_post

> models::V1AdminLoginPost200Response v1_admin_login_post(v1_admin_login_post_request)
Tenant-admin email+password login

Exchanges an admin's email + password for a session token. The web console at `app.lockally.com` posts this on form submission and stores the returned token in an httpOnly cookie.  **No enumeration leak.** Wrong-email and wrong-password both return the same 401 with title \"Invalid credentials\". The argon2id verify runs even on lookup miss (well, structurally — the lookup fails fast but the response shape is constant) so timing leaks are bounded.  Tokens are prefixed `adm_sess_` and valid for 7 days. Use as the `Authorization: Bearer` value on all subsequent calls. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**v1_admin_login_post_request** | [**V1AdminLoginPostRequest**](V1AdminLoginPostRequest.md) |  | [required] |

### Return type

[**models::V1AdminLoginPost200Response**](_v1_admin_login_post_200_response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_admin_logout_post

> v1_admin_logout_post()
Invalidate the current admin session

Deletes the session row from the database. Idempotent — calling logout on an already-invalid token returns 204 anyway. 

### Parameters

This endpoint does not need any parameter.

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_admin_me_get

> models::V1AdminMeGet200Response v1_admin_me_get()
Get the current admin + tenant

Returns the admin profile + tenant for the session token presented in `Authorization: Bearer`. Used by the web console's layout load function to populate the sidebar.  Returns 403 if called with an API key (lk_live_*) bearer — admin context only exists for session tokens. 

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::V1AdminMeGet200Response**](_v1_admin_me_get_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

