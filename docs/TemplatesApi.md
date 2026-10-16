# \TemplatesApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_template**](TemplatesApi.md#create_template) | **POST** /v1/templates | Create a template
[**delete_template**](TemplatesApi.md#delete_template) | **DELETE** /v1/templates/{id} | Delete a template
[**get_template**](TemplatesApi.md#get_template) | **GET** /v1/templates/{id} | Get a template
[**list_templates**](TemplatesApi.md#list_templates) | **GET** /v1/templates | List templates
[**update_template**](TemplatesApi.md#update_template) | **PUT** /v1/templates/{id} | Update a template



## create_template

> models::Template create_template(template_input)
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


## delete_template

> delete_template(id)
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


## get_template

> models::Template get_template(id)
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


## list_templates

> models::ListTemplates200Response list_templates()
List templates

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::ListTemplates200Response**](listTemplates_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_template

> models::Template update_template(id, template_input)
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

