# \EncryptionApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**batch_lookup_public_keys**](EncryptionApi.md#batch_lookup_public_keys) | **GET** /v1/encryption/keys/lookup | Batch-lookup public keys by email
[**create_encryption_key**](EncryptionApi.md#create_encryption_key) | **POST** /v1/encryption/keys | Upload an encryption key pair
[**create_encryption_recovery**](EncryptionApi.md#create_encryption_recovery) | **POST** /v1/encryption/recovery | Store an encryption recovery blob
[**get_encryption_key**](EncryptionApi.md#get_encryption_key) | **GET** /v1/encryption/keys/{email} | Get encryption key for a mailbox
[**get_encryption_status**](EncryptionApi.md#get_encryption_status) | **GET** /v1/encryption/status | End-to-end encryption status for the workspace
[**rotate_encryption_key**](EncryptionApi.md#rotate_encryption_key) | **POST** /v1/encryption/keys/rotate | Re-seal an encryption key under a new password



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

Only the mailbox's own webmail session may call this; an API key is refused with 403. The private key is sealed under that mailbox's password, which an administrator never has. `mailbox_email`, if sent, must be the caller's own mailbox. A mailbox that already has a key is starting over: the old key is kept inactive, not destroyed, and the new one starts without a recovery code.

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

Only the mailbox's own webmail session may call this; an API key is refused with 403. The private key is sealed under that mailbox's password, which an administrator never has. `mailbox_email`, if sent, must be the caller's own mailbox. The blob is the private key sealed under a recovery code the browser generated; the code itself is never sent. Replaces any earlier one.

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

Anyone in the workspace gets the public key. The mailbox's own webmail session also gets its sealed private key, its sealed recovery copy and the recovery state.

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


## get_encryption_status

> models::GetEncryptionStatus200Response get_encryption_status()
End-to-end encryption status for the workspace

For administrators: whether the add-on is on, and for each mailbox whether it has a key and a recovery code. Carries no key material.

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::GetEncryptionStatus200Response**](getEncryptionStatus_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## rotate_encryption_key

> rotate_encryption_key(rotate_encryption_key_request)
Re-seal an encryption key under a new password

Only the mailbox's own webmail session may call this; an API key is refused with 403. The private key is sealed under that mailbox's password, which an administrator never has. `mailbox_email`, if sent, must be the caller's own mailbox. The key pair does not change, so every message stays readable.

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

