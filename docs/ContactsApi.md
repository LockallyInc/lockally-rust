# \ContactsApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**bulk_upsert_external_contacts**](ContactsApi.md#bulk_upsert_external_contacts) | **PUT** /v1/contacts/external/{system} | Create or update up to 500 contacts by their ids in another system
[**create_contact**](ContactsApi.md#create_contact) | **POST** /v1/contacts | Create a contact
[**delete_contact**](ContactsApi.md#delete_contact) | **DELETE** /v1/contacts/{id} | Delete a contact
[**delete_external_contact**](ContactsApi.md#delete_external_contact) | **DELETE** /v1/contacts/external/{system}/{external_id} | Delete a contact by its id in another system
[**get_contact**](ContactsApi.md#get_contact) | **GET** /v1/contacts/{id} | Get a contact
[**get_contact_lists**](ContactsApi.md#get_contact_lists) | **GET** /v1/contacts/{id}/lists | Get lists a contact belongs to
[**get_external_contact**](ContactsApi.md#get_external_contact) | **GET** /v1/contacts/external/{system}/{external_id} | Get a contact by its id in another system
[**list_contacts**](ContactsApi.md#list_contacts) | **GET** /v1/contacts | List contacts
[**update_contact**](ContactsApi.md#update_contact) | **PATCH** /v1/contacts/{id} | Update a contact
[**upsert_external_contact**](ContactsApi.md#upsert_external_contact) | **PUT** /v1/contacts/external/{system}/{external_id} | Create or update a contact by its id in another system



## bulk_upsert_external_contacts

> models::BulkUpsertExternalContacts200Response bulk_upsert_external_contacts(system, bulk_upsert_external_contacts_request)
Create or update up to 500 contacts by their ids in another system

For a sync. Each row stands alone: a bad row is reported in `results` with its index and the rest are stored, so the response is 200 whenever the request itself is well formed. Read `failed` and `results`. Two rows with the same `external_id` in one request are refused (the later one), because which is current cannot be known. Rerunning the same payload updates rather than duplicates.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**system** | **String** |  | [required] |
**bulk_upsert_external_contacts_request** | [**BulkUpsertExternalContactsRequest**](BulkUpsertExternalContactsRequest.md) |  | [required] |

### Return type

[**models::BulkUpsertExternalContacts200Response**](bulkUpsertExternalContacts_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


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


## delete_external_contact

> delete_external_contact(system, external_id)
Delete a contact by its id in another system

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**system** | **String** | Your label for the system the record comes from, for example `salesforce`, `hubspot` or `odoo`. 1 to 64 characters: lowercase letters, digits, dot, underscore or hyphen (upper case is folded). | [required] |
**external_id** | **String** | The record's id in that system, kept exactly as given (case matters). 1 to 255 characters, no spaces. URL-encode it. | [required] |

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


## get_external_contact

> models::Contact get_external_contact(system, external_id)
Get a contact by its id in another system

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**system** | **String** | Your label for the system the record comes from, for example `salesforce`, `hubspot` or `odoo`. 1 to 64 characters: lowercase letters, digits, dot, underscore or hyphen (upper case is folded). | [required] |
**external_id** | **String** | The record's id in that system, kept exactly as given (case matters). 1 to 255 characters, no spaces. URL-encode it. | [required] |

### Return type

[**models::Contact**](Contact.md)

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


## upsert_external_contact

> models::Contact upsert_external_contact(system, external_id, external_contact_input)
Create or update a contact by its id in another system

Idempotent: the path is the identity, so sending the same request twice cannot create a second contact, and you never need to store our id. Returns 201 when the contact was created and 200 when it already existed. The body is the full representation: a field you leave out is cleared. Email is an ordinary attribute, not a key, so changing it updates the same contact. `mailboxes:write` is also accepted.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**system** | **String** | Your label for the system the record comes from, for example `salesforce`, `hubspot` or `odoo`. 1 to 64 characters: lowercase letters, digits, dot, underscore or hyphen (upper case is folded). | [required] |
**external_id** | **String** | The record's id in that system, kept exactly as given (case matters). 1 to 255 characters, no spaces. URL-encode it. | [required] |
**external_contact_input** | [**ExternalContactInput**](ExternalContactInput.md) |  | [required] |

### Return type

[**models::Contact**](Contact.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

