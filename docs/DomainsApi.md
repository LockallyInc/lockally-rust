# \DomainsApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_domain**](DomainsApi.md#create_domain) | **POST** /v1/domains | Register a domain
[**delete_domain**](DomainsApi.md#delete_domain) | **DELETE** /v1/domains/{domain} | Delete a domain
[**disable_return_path**](DomainsApi.md#disable_return_path) | **DELETE** /v1/domains/{domain}/return-path | Turn off the custom Return-Path
[**enable_return_path**](DomainsApi.md#enable_return_path) | **POST** /v1/domains/{domain}/return-path | Turn on the custom Return-Path
[**get_domain**](DomainsApi.md#get_domain) | **GET** /v1/domains/{domain} | Get a domain
[**get_return_path**](DomainsApi.md#get_return_path) | **GET** /v1/domains/{domain}/return-path | Get the custom Return-Path
[**list_domains**](DomainsApi.md#list_domains) | **GET** /v1/domains | List domains
[**verify_domain**](DomainsApi.md#verify_domain) | **POST** /v1/domains/{domain}/verify | Force-poll DNS verification
[**verify_return_path**](DomainsApi.md#verify_return_path) | **POST** /v1/domains/{domain}/return-path/verify | Check the custom Return-Path records



## create_domain

> models::Domain create_domain(create_domain_request)
Register a domain

Registers a new domain for the calling tenant. Generates a DKIM keypair and verification token. Returns DNS instructions the tenant must publish under their own DNS (verification TXT, SPF include, DKIM TXT, MX records to `mx1`/`mx2.lockally.com`, DMARC seed).  **Idempotent**, re-posting the same domain returns the existing record with the same DKIM keys and token (regenerating would break the tenant's published DNS). Returns 200 on idempotent hit, 201 on first create.  Returns 409 if the domain is already claimed by a different tenant. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**create_domain_request** | [**CreateDomainRequest**](CreateDomainRequest.md) |  | [required] |

### Return type

[**models::Domain**](Domain.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_domain

> delete_domain(domain)
Delete a domain

Removes the domain registration. Refuses with 409 if any mailbox is still attached, delete the mailboxes first. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**domain** | **String** |  | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## disable_return_path

> disable_return_path(domain)
Turn off the custom Return-Path

API mail uses the sender's own address as the envelope sender again, from the next message. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**domain** | **String** |  | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## enable_return_path

> models::ReturnPath enable_return_path(domain)
Turn on the custom Return-Path

Moves it to `pending` and returns the two records to publish on `bounces.<domain>`. Nothing changes for mail until they are confirmed with the verify call. The domain must be verified. Available on every plan except Free. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**domain** | **String** |  | [required] |

### Return type

[**models::ReturnPath**](ReturnPath.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_domain

> models::Domain get_domain(domain)
Get a domain

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**domain** | **String** |  | [required] |

### Return type

[**models::Domain**](Domain.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_return_path

> models::ReturnPath get_return_path(domain)
Get the custom Return-Path

A custom Return-Path moves the envelope sender of mail sent through the API from this domain onto `bounces.<domain>`. Bounce reports then come back to Lockally instead of the sending mailbox, and a bounce that arrives after delivery marks the message bounced, suppresses the address and fires `delivery.bounced`. Mail sent from webmail or mail apps is not affected. DKIM stays signed by the domain itself. `status` is `off`, `pending` (records not confirmed yet) or `active`. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**domain** | **String** |  | [required] |

### Return type

[**models::ReturnPath**](ReturnPath.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_domains

> models::ListDomains200Response list_domains()
List domains

Returns every domain registered under the calling tenant.

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::ListDomains200Response**](listDomains_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## verify_domain

> models::Domain verify_domain(domain)
Force-poll DNS verification

Synchronously checks the `_lockally-verify.<domain>` TXT record against the stored verification token. Returns 200 either way: the returned `verified` boolean tells you whether DNS now confirms. Caller polls until `verified: true`. A later version may have the platform auto-polls and fires a `domain.verified` webhook. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**domain** | **String** |  | [required] |

### Return type

[**models::Domain**](Domain.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## verify_return_path

> models::ReturnPath verify_return_path(domain)
Check the custom Return-Path records

Looks up the MX and SPF records on `bounces.<domain>`. Returns 200 either way: while a record is missing the status stays `pending` and `check` says which one. Once both are found the Return-Path becomes `active` and the send path starts using it. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**domain** | **String** |  | [required] |

### Return type

[**models::ReturnPath**](ReturnPath.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

