# \TemplatesApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**v1_templates_get**](TemplatesApi.md#v1_templates_get) | **GET** /v1/templates | List templates
[**v1_templates_id_delete**](TemplatesApi.md#v1_templates_id_delete) | **DELETE** /v1/templates/{id} | Delete a template
[**v1_templates_id_get**](TemplatesApi.md#v1_templates_id_get) | **GET** /v1/templates/{id} | Get a template
[**v1_templates_id_put**](TemplatesApi.md#v1_templates_id_put) | **PUT** /v1/templates/{id} | Update a template
[**v1_templates_post**](TemplatesApi.md#v1_templates_post) | **POST** /v1/templates | Create a template



## v1_templates_get

> models::V1TemplatesGet200Response v1_templates_get()
List templates

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::V1TemplatesGet200Response**](_v1_templates_get_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_templates_id_delete

> v1_templates_id_delete(id)
Delete a template

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


## v1_templates_id_get

> models::Template v1_templates_id_get(id)
Get a template

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::Template**](Template.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_templates_id_put

> models::Template v1_templates_id_put(id, template_input)
Update a template

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |
**template_input** | [**TemplateInput**](TemplateInput.md) |  | [required] |

### Return type

[**models::Template**](Template.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_templates_post

> models::Template v1_templates_post(template_input)
Create a template

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**template_input** | [**TemplateInput**](TemplateInput.md) |  | [required] |

### Return type

[**models::Template**](Template.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

