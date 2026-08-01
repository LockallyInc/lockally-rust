# \DomainsApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**v1_domains_domain_delete**](DomainsApi.md#v1_domains_domain_delete) | **DELETE** /v1/domains/{domain} | Delete a domain
[**v1_domains_domain_get**](DomainsApi.md#v1_domains_domain_get) | **GET** /v1/domains/{domain} | Get a domain
[**v1_domains_domain_verify_post**](DomainsApi.md#v1_domains_domain_verify_post) | **POST** /v1/domains/{domain}/verify | Force-poll DNS verification
[**v1_domains_get**](DomainsApi.md#v1_domains_get) | **GET** /v1/domains | List domains
[**v1_domains_post**](DomainsApi.md#v1_domains_post) | **POST** /v1/domains | Register a domain



## v1_domains_domain_delete

> v1_domains_domain_delete(domain)
Delete a domain

Removes the domain registration. Refuses with 409 if any mailbox is still attached — delete the mailboxes first. 

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


## v1_domains_domain_get

> models::Domain v1_domains_domain_get(domain)
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


## v1_domains_domain_verify_post

> models::Domain v1_domains_domain_verify_post(domain)
Force-poll DNS verification

Synchronously checks the `_lockally-verify.<domain>` TXT record against the stored verification token. Returns 200 either way: the returned `verified` boolean tells you whether DNS now confirms. Caller polls until `verified: true`. In v2 a background worker auto-polls and fires a `domain.verified` webhook. 

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


## v1_domains_get

> models::V1DomainsGet200Response v1_domains_get()
List domains

Returns every domain registered under the calling tenant.

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::V1DomainsGet200Response**](_v1_domains_get_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1_domains_post

> models::Domain v1_domains_post(v1_domains_post_request)
Register a domain

Registers a new domain for the calling tenant. Generates a DKIM keypair and verification token. Returns DNS instructions the tenant must publish under their own DNS (verification TXT, SPF include, DKIM TXT, MX records to `mx1`/`mx2.lockally.com`, DMARC seed).  **Idempotent** — re-posting the same domain returns the existing record with the same DKIM keys and token (regenerating would break the tenant's published DNS). Returns 200 on idempotent hit, 201 on first create.  Returns 409 if the domain is already claimed by a different tenant. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**v1_domains_post_request** | [**V1DomainsPostRequest**](V1DomainsPostRequest.md) |  | [required] |

### Return type

[**models::Domain**](Domain.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

