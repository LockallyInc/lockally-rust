# \ContactsApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_contact**](ContactsApi.md#create_contact) | **POST** /v1/contacts | Create a contact
[**delete_contact**](ContactsApi.md#delete_contact) | **DELETE** /v1/contacts/{id} | Delete a contact
[**get_contact**](ContactsApi.md#get_contact) | **GET** /v1/contacts/{id} | Get a contact
[**get_contact_lists**](ContactsApi.md#get_contact_lists) | **GET** /v1/contacts/{id}/lists | Get lists a contact belongs to
[**list_contacts**](ContactsApi.md#list_contacts) | **GET** /v1/contacts | List contacts
[**update_contact**](ContactsApi.md#update_contact) | **PATCH** /v1/contacts/{id} | Update a contact



## create_contact

> models::Contact create_contact(create_contact_request)
Create a contact

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**create_contact_request** | [**CreateContactRequest**](CreateContactRequest.md) |  | [required] |

### Return type

[**models::Contact**](Contact.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_contact

> delete_contact(id)
Delete a contact

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


## get_contact

> models::Contact get_contact(id)
Get a contact

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::Contact**](Contact.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_contact_lists

> models::GetContactLists200Response get_contact_lists(id)
Get lists a contact belongs to

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::GetContactLists200Response**](getContactLists_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_contacts

> models::ListContacts200Response list_contacts(q, r#type, department, status, source)
List contacts

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**q** | Option<**String**> | Free-text search across name, email, company |  |
**r#type** | Option<**String**> | Filter by contact_type |  |
**department** | Option<**String**> | Filter by department |  |
**status** | Option<**String**> | Filter by status |  |
**source** | Option<**String**> | Filter by source |  |

### Return type

[**models::ListContacts200Response**](listContacts_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_contact

> models::Contact update_contact(id, update_contact_request)
Update a contact

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |
**update_contact_request** | [**UpdateContactRequest**](UpdateContactRequest.md) |  | [required] |

### Return type

[**models::Contact**](Contact.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

