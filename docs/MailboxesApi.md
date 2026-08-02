# \MailboxesApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_shared_member**](MailboxesApi.md#add_shared_member) | **POST** /v1/mailboxes/{email}/members | Add a shared mailbox member
[**list_shared_members**](MailboxesApi.md#list_shared_members) | **GET** /v1/mailboxes/{email}/members | List shared mailbox members
[**remove_shared_member**](MailboxesApi.md#remove_shared_member) | **DELETE** /v1/mailboxes/{email}/members/{memberEmail} | Remove a shared mailbox member
[**v1_mailboxes_email_delete**](MailboxesApi.md#v1_mailboxes_email_delete) | **DELETE** /v1/mailboxes/{email} | Soft-delete a mailbox
[**v1_mailboxes_email_export_download_get**](MailboxesApi.md#v1_mailboxes_email_export_download_get) | **GET** /v1/mailboxes/{email}/export/download | Download a previously-issued mailbox export
[**v1_mailboxes_email_export_post**](MailboxesApi.md#v1_mailboxes_email_export_post) | **POST** /v1/mailboxes/{email}/export | Request a mailbox export
[**v1_mailboxes_email_get**](MailboxesApi.md#v1_mailboxes_email_get) | **GET** /v1/mailboxes/{email} | Get a mailbox
[**v1_mailboxes_email_patch**](MailboxesApi.md#v1_mailboxes_email_patch) | **PATCH** /v1/mailboxes/{email} | Update a mailbox
[**v1_mailboxes_email_vacation_delete**](MailboxesApi.md#v1_mailboxes_email_vacation_delete) | **DELETE** /v1/mailboxes/{email}/vacation | Remove the vacation responder
[**v1_mailboxes_email_vacation_get**](MailboxesApi.md#v1_mailboxes_email_vacation_get) | **GET** /v1/mailboxes/{email}/vacation | Get the vacation responder
[**v1_mailboxes_email_vacation_put**](MailboxesApi.md#v1_mailboxes_email_vacation_put) | **PUT** /v1/mailboxes/{email}/vacation | Set the vacation responder
[**v1_mailboxes_get**](MailboxesApi.md#v1_mailboxes_get) | **GET** /v1/mailboxes | List mailboxes
[**v1_mailboxes_post**](MailboxesApi.md#v1_mailboxes_post) | **POST** /v1/mailboxes | Create a mailbox
[**v1_vacation_get**](MailboxesApi.md#v1_vacation_get) | **GET** /v1/vacation | List all vacation responders



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


## v1_mailboxes_email_delete

> v1_mailboxes_email_delete(email)
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


## v1_mailboxes_email_export_download_get

> std::path::PathBuf v1_mailboxes_email_export_download_get(email, token)
Download a previously-issued mailbox export

Public endpoint (no Authorization header). Validates the one-shot token from the URL, marks it used, and streams an mbox file. Second GET with the same token returns 404 — tokens are single-use. 

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


## v1_mailboxes_email_export_post

> models::V1MailboxesEmailExportPost201Response v1_mailboxes_email_export_post(email)
Request a mailbox export

Issues a one-shot \"presigned\" download URL for the mailbox's content in mbox format. The URL works without an Authorization header — the token in the query string is the authz. TTL is 5 minutes; the token is consumed on first GET.  **v1 caveat:** the synthesized mbox only contains outbound mail (from `lockally.messages`). v2 swaps in Stalwart's export primitive for full inbox + folder structure + flags. The endpoint contract stays unchanged. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**email** | **String** |  | [required] |

### Return type

[**models::V1MailboxesEmailExportPost201Response**](_v1_mailboxes__email__export_post_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_mailboxes_email_get

> models::Mailbox v1_mailboxes_email_get(email)
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


## v1_mailboxes_email_patch

> models::Mailbox v1_mailboxes_email_patch(email, v1_mailboxes_email_patch_request)
Update a mailbox

Supply at least one of `password`, `quota_bytes`, `disabled`. Returns the updated mailbox. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**email** | **String** |  | [required] |
**v1_mailboxes_email_patch_request** | [**V1MailboxesEmailPatchRequest**](V1MailboxesEmailPatchRequest.md) |  | [required] |

### Return type

[**models::Mailbox**](Mailbox.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_mailboxes_email_vacation_delete

> v1_mailboxes_email_vacation_delete(email)
Remove the vacation responder

Idempotent — 204 whether or not a row existed.

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


## v1_mailboxes_email_vacation_get

> models::VacationResponder v1_mailboxes_email_vacation_get(email)
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


## v1_mailboxes_email_vacation_put

> models::VacationResponder v1_mailboxes_email_vacation_put(email, v1_mailboxes_email_vacation_put_request)
Set the vacation responder

Upsert — same endpoint creates or replaces the rule. Clears `synced_at`; the rule is staged on lockally until a sync worker pushes it to the mail server. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**email** | **String** |  | [required] |
**v1_mailboxes_email_vacation_put_request** | [**V1MailboxesEmailVacationPutRequest**](V1MailboxesEmailVacationPutRequest.md) |  | [required] |

### Return type

[**models::VacationResponder**](VacationResponder.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_mailboxes_get

> models::V1MailboxesGet200Response v1_mailboxes_get(limit)
List mailboxes

Returns mailboxes under the calling tenant — active and soft-deleted. `?limit=N` between 1 and 200 (default 50). 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**limit** | Option<**u32**> |  |  |[default to 50]

### Return type

[**models::V1MailboxesGet200Response**](_v1_mailboxes_get_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_mailboxes_post

> models::Mailbox v1_mailboxes_post(v1_mailboxes_post_request)
Create a mailbox

Creates a mailbox on a tenant-verified domain. If `password` is omitted, lockally generates a 16-char password and returns it in the response — shown once.  **Gate.** The mailbox's domain must already be registered AND verified for this tenant (via `/v1/domains` + `/v1/domains/{domain}/verify`).  **Idempotent.** Re-posting the same email returns the existing mailbox UNTOUCHED — password is NOT regenerated. To change a password, use PATCH instead. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**v1_mailboxes_post_request** | [**V1MailboxesPostRequest**](V1MailboxesPostRequest.md) |  | [required] |

### Return type

[**models::Mailbox**](Mailbox.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_vacation_get

> models::V1VacationGet200Response v1_vacation_get()
List all vacation responders

Returns every vacation responder for the calling tenant.

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::V1VacationGet200Response**](_v1_vacation_get_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

