# \MailboxesApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_shared_member**](MailboxesApi.md#add_shared_member) | **POST** /v1/mailboxes/{email}/members | Add a shared mailbox member
[**create_mailbox**](MailboxesApi.md#create_mailbox) | **POST** /v1/mailboxes | Create a mailbox
[**delete_mailbox**](MailboxesApi.md#delete_mailbox) | **DELETE** /v1/mailboxes/{email} | Soft-delete a mailbox
[**delete_vacation_responder**](MailboxesApi.md#delete_vacation_responder) | **DELETE** /v1/mailboxes/{email}/vacation | Remove the vacation responder
[**download_mailbox_export**](MailboxesApi.md#download_mailbox_export) | **GET** /v1/mailboxes/{email}/export/download | Download a previously-issued mailbox export
[**export_mailbox**](MailboxesApi.md#export_mailbox) | **POST** /v1/mailboxes/{email}/export | Request a mailbox export
[**get_mailbox**](MailboxesApi.md#get_mailbox) | **GET** /v1/mailboxes/{email} | Get a mailbox
[**get_vacation_responder**](MailboxesApi.md#get_vacation_responder) | **GET** /v1/mailboxes/{email}/vacation | Get the vacation responder
[**list_mailboxes**](MailboxesApi.md#list_mailboxes) | **GET** /v1/mailboxes | List mailboxes
[**list_shared_members**](MailboxesApi.md#list_shared_members) | **GET** /v1/mailboxes/{email}/members | List shared mailbox members
[**list_vacation_responders**](MailboxesApi.md#list_vacation_responders) | **GET** /v1/vacation | List all vacation responders
[**remove_shared_member**](MailboxesApi.md#remove_shared_member) | **DELETE** /v1/mailboxes/{email}/members/{memberEmail} | Remove a shared mailbox member
[**set_vacation_responder**](MailboxesApi.md#set_vacation_responder) | **PUT** /v1/mailboxes/{email}/vacation | Set the vacation responder
[**update_mailbox**](MailboxesApi.md#update_mailbox) | **PATCH** /v1/mailboxes/{email} | Update a mailbox



## add_shared_member

> models::SharedMember add_shared_member(email, add_shared_member_request)
Add a shared mailbox member

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**email** | **String** |  | [required] |
**add_shared_member_request** | [**AddSharedMemberRequest**](AddSharedMemberRequest.md) |  | [required] |

### Return type

[**models::SharedMember**](SharedMember.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_mailbox

> models::Mailbox create_mailbox(create_mailbox_request)
Create a mailbox

Creates a mailbox on a tenant-verified domain. If `password` is omitted, lockally generates a 16-char password and returns it in the response, shown once.  **Gate.** The mailbox's domain must already be registered AND verified for this tenant (via `/v1/domains` + `/v1/domains/{domain}/verify`).  **Idempotent.** Re-posting the same email returns the existing mailbox UNTOUCHED, password is NOT regenerated. To change a password, use PATCH instead. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**create_mailbox_request** | [**CreateMailboxRequest**](CreateMailboxRequest.md) |  | [required] |

### Return type

[**models::Mailbox**](Mailbox.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_mailbox

> delete_mailbox(email)
Soft-delete a mailbox

Sets `soft_deleted_at = now()` and `hard_delete_after = now() + 90d` per design D25. A background sweep (planned) will hard-delete after the window. The mailbox is also disabled immediately. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**email** | **String** |  | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_vacation_responder

> delete_vacation_responder(email)
Remove the vacation responder

Idempotent, 204 whether or not a row existed.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**email** | **String** |  | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## download_mailbox_export

> std::path::PathBuf download_mailbox_export(email, token)
Download a previously-issued mailbox export

Public endpoint (no Authorization header). Validates the one-shot token from the URL, marks it used, and streams an mbox file. Second GET with the same token returns 404, tokens are single-use. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**email** | **String** |  | [required] |
**token** | **String** |  | [required] |

### Return type

[**std::path::PathBuf**](std::path::PathBuf.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/mbox, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## export_mailbox

> models::ExportMailbox201Response export_mailbox(email)
Request a mailbox export

Issues a one-shot \"presigned\" download URL for the mailbox's content in mbox format. The URL works without an Authorization header, the token in the query string is the authz. TTL is 5 minutes; the token is consumed on first GET.  **v1 caveat:** the synthesized mbox only contains outbound mail (sent mail only). A later version will cover received mail for full inbox + folder structure + flags. The endpoint contract stays unchanged.  **Scope changed:** this used to accept `mailboxes:read`. It takes any mailbox in the tenant and returns that mailbox's mail, so it now requires `tenant:admin`, matching `POST /v1/ediscovery/export`. A key scoped `mailboxes:read` gets 403 and has to be reissued; admin console sessions are unaffected. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**email** | **String** |  | [required] |

### Return type

[**models::ExportMailbox201Response**](exportMailbox_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_mailbox

> models::Mailbox get_mailbox(email)
Get a mailbox

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**email** | **String** |  | [required] |

### Return type

[**models::Mailbox**](Mailbox.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_vacation_responder

> models::VacationResponder get_vacation_responder(email)
Get the vacation responder

Returns the stored vacation rule or 404 if none is set.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**email** | **String** |  | [required] |

### Return type

[**models::VacationResponder**](VacationResponder.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_mailboxes

> models::ListMailboxes200Response list_mailboxes(limit)
List mailboxes

Returns mailboxes under the calling tenant, active and soft-deleted. `?limit=N` between 1 and 200 (default 50). 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**limit** | Option<**u32**> |  |  |[default to 50]

### Return type

[**models::ListMailboxes200Response**](listMailboxes_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_shared_members

> models::ListSharedMembers200Response list_shared_members(email)
List shared mailbox members

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**email** | **String** |  | [required] |

### Return type

[**models::ListSharedMembers200Response**](listSharedMembers_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_vacation_responders

> models::ListVacationResponders200Response list_vacation_responders()
List all vacation responders

Returns every vacation responder for the calling tenant.

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::ListVacationResponders200Response**](listVacationResponders_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## remove_shared_member

> remove_shared_member(email, member_email)
Remove a shared mailbox member

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**email** | **String** |  | [required] |
**member_email** | **String** |  | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## set_vacation_responder

> models::VacationResponder set_vacation_responder(email, set_vacation_responder_request)
Set the vacation responder

Upsert, same endpoint creates or replaces the rule. Clears `synced_at`; the rule is staged until a later sync pushes it to the mail server. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**email** | **String** |  | [required] |
**set_vacation_responder_request** | [**SetVacationResponderRequest**](SetVacationResponderRequest.md) |  | [required] |

### Return type

[**models::VacationResponder**](VacationResponder.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_mailbox

> models::Mailbox update_mailbox(email, update_mailbox_request)
Update a mailbox

Supply at least one of `password`, `quota_bytes`, `disabled`. Returns the updated mailbox. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**email** | **String** |  | [required] |
**update_mailbox_request** | [**UpdateMailboxRequest**](UpdateMailboxRequest.md) |  | [required] |

### Return type

[**models::Mailbox**](Mailbox.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

