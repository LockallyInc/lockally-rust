# \ContactListsApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_contact_list_member**](ContactListsApi.md#add_contact_list_member) | **POST** /v1/contact-lists/{id}/members | Add a member to a contact list
[**create_contact_list**](ContactListsApi.md#create_contact_list) | **POST** /v1/contact-lists | Create a contact list
[**delete_contact_list**](ContactListsApi.md#delete_contact_list) | **DELETE** /v1/contact-lists/{id} | Delete a contact list
[**get_contact_list**](ContactListsApi.md#get_contact_list) | **GET** /v1/contact-lists/{id} | Get a contact list with members
[**list_contact_lists**](ContactListsApi.md#list_contact_lists) | **GET** /v1/contact-lists | List contact lists
[**remove_contact_list_member**](ContactListsApi.md#remove_contact_list_member) | **DELETE** /v1/contact-lists/{id}/members/{contactId} | Remove a member from a contact list
[**update_contact_list**](ContactListsApi.md#update_contact_list) | **PATCH** /v1/contact-lists/{id} | Update a contact list



## add_contact_list_member

> add_contact_list_member(id, add_contact_list_member_request)
Add a member to a contact list

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |
**add_contact_list_member_request** | [**AddContactListMemberRequest**](AddContactListMemberRequest.md) |  | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_contact_list

> models::ContactList create_contact_list(create_contact_list_request)
Create a contact list

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**create_contact_list_request** | [**CreateContactListRequest**](CreateContactListRequest.md) |  | [required] |

### Return type

[**models::ContactList**](ContactList.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_contact_list

> delete_contact_list(id)
Delete a contact list

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


## get_contact_list

> models::GetContactList200Response get_contact_list(id)
Get a contact list with members

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::GetContactList200Response**](getContactList_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_contact_lists

> models::ListContactLists200Response list_contact_lists()
List contact lists

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::ListContactLists200Response**](listContactLists_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## remove_contact_list_member

> remove_contact_list_member(id, contact_id)
Remove a member from a contact list

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |
**contact_id** | **uuid::Uuid** |  | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_contact_list

> models::ContactList update_contact_list(id, update_contact_list_request)
Update a contact list

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |
**update_contact_list_request** | [**UpdateContactListRequest**](UpdateContactListRequest.md) |  | [required] |

### Return type

[**models::ContactList**](ContactList.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

