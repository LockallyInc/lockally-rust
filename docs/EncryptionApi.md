# \EncryptionApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**batch_lookup_public_keys**](EncryptionApi.md#batch_lookup_public_keys) | **GET** /v1/encryption/keys/lookup | Batch-lookup public keys by email
[**create_encryption_key**](EncryptionApi.md#create_encryption_key) | **POST** /v1/encryption/keys | Upload an encryption key pair
[**create_encryption_recovery**](EncryptionApi.md#create_encryption_recovery) | **POST** /v1/encryption/recovery | Store an encryption recovery blob
[**get_encryption_key**](EncryptionApi.md#get_encryption_key) | **GET** /v1/encryption/keys/{email} | Get encryption key for a mailbox
[**rotate_encryption_key**](EncryptionApi.md#rotate_encryption_key) | **POST** /v1/encryption/keys/rotate | Rotate an encryption key



## batch_lookup_public_keys

> models::BatchLookupPublicKeys200Response batch_lookup_public_keys(emails)
Batch-lookup public keys by email

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**emails** | **String** | Comma-separated list of email addresses | [required] |

### Return type

[**models::BatchLookupPublicKeys200Response**](batchLookupPublicKeys_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_encryption_key

> models::CreateEncryptionKey201Response create_encryption_key(create_encryption_key_request)
Upload an encryption key pair

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**create_encryption_key_request** | [**CreateEncryptionKeyRequest**](CreateEncryptionKeyRequest.md) |  | [required] |

### Return type

[**models::CreateEncryptionKey201Response**](createEncryptionKey_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_encryption_recovery

> create_encryption_recovery(create_encryption_recovery_request)
Store an encryption recovery blob

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**create_encryption_recovery_request** | [**CreateEncryptionRecoveryRequest**](CreateEncryptionRecoveryRequest.md) |  | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_encryption_key

> models::GetEncryptionKey200Response get_encryption_key(email)
Get encryption key for a mailbox

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**email** | **String** |  | [required] |

### Return type

[**models::GetEncryptionKey200Response**](getEncryptionKey_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## rotate_encryption_key

> rotate_encryption_key(rotate_encryption_key_request)
Rotate an encryption key

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**rotate_encryption_key_request** | [**RotateEncryptionKeyRequest**](RotateEncryptionKeyRequest.md) |  | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

