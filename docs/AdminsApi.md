# \AdminsApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**v1_admins_get**](AdminsApi.md#v1_admins_get) | **GET** /v1/admins | List tenant admins
[**v1_admins_id_delete**](AdminsApi.md#v1_admins_id_delete) | **DELETE** /v1/admins/{id} | Delete an admin
[**v1_admins_id_patch**](AdminsApi.md#v1_admins_id_patch) | **PATCH** /v1/admins/{id} | Update an admin
[**v1_admins_post**](AdminsApi.md#v1_admins_post) | **POST** /v1/admins | Invite a new admin



## v1_admins_get

> models::V1AdminsGet200Response v1_admins_get()
List tenant admins

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::V1AdminsGet200Response**](_v1_admins_get_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_admins_id_delete

> v1_admins_id_delete(id)
Delete an admin

Hard-delete. Cascade-drops the admin's sessions (immediate revocation). Same safety rails as PATCH disabled=true. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_admins_id_patch

> models::AdminFull v1_admins_id_patch(id, v1_admins_id_patch_request)
Update an admin

Supply at least one of `password`, `display_name`, `role`, `disabled`.  **Safety rails.** A session bearer (adm_sess_*) cannot disable itself — use another admin or an API key (which bypasses the self-rail). Disabling the last active admin returns 409 to prevent orphaning the tenant from its console. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |
**v1_admins_id_patch_request** | [**V1AdminsIdPatchRequest**](V1AdminsIdPatchRequest.md) |  | [required] |

### Return type

[**models::AdminFull**](AdminFull.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_admins_post

> models::AdminFull v1_admins_post(v1_admins_post_request)
Invite a new admin

Creates a new tenant admin. If `password` is omitted, lockally generates a 16-char password and returns it ONCE in the response. Email is case-insensitive and unique per tenant. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**v1_admins_post_request** | [**V1AdminsPostRequest**](V1AdminsPostRequest.md) |  | [required] |

### Return type

[**models::AdminFull**](AdminFull.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

