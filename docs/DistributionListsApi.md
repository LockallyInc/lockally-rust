# \DistributionListsApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_distribution_list**](DistributionListsApi.md#create_distribution_list) | **POST** /v1/distribution-lists | Create a distribution list
[**delete_distribution_list**](DistributionListsApi.md#delete_distribution_list) | **DELETE** /v1/distribution-lists/{address} | Delete a distribution list
[**get_distribution_list**](DistributionListsApi.md#get_distribution_list) | **GET** /v1/distribution-lists/{address} | Get a distribution list
[**list_distribution_lists**](DistributionListsApi.md#list_distribution_lists) | **GET** /v1/distribution-lists | List distribution lists
[**replace_distribution_list_members**](DistributionListsApi.md#replace_distribution_list_members) | **PUT** /v1/distribution-lists/{address}/members | Replace distribution list members



## create_distribution_list

> models::DistributionListDetail create_distribution_list(create_distribution_list_request)
Create a distribution list

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**create_distribution_list_request** | [**CreateDistributionListRequest**](CreateDistributionListRequest.md) |  | [required] |

### Return type

[**models::DistributionListDetail**](DistributionListDetail.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_distribution_list

> delete_distribution_list(address)
Delete a distribution list

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**address** | **String** | Distribution list email address | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_distribution_list

> models::DistributionListDetail get_distribution_list(address)
Get a distribution list

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**address** | **String** | Distribution list email address | [required] |

### Return type

[**models::DistributionListDetail**](DistributionListDetail.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_distribution_lists

> models::ListDistributionLists200Response list_distribution_lists()
List distribution lists

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::ListDistributionLists200Response**](listDistributionLists_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## replace_distribution_list_members

> models::ReplaceDistributionListMembers200Response replace_distribution_list_members(address, replace_distribution_list_members_request)
Replace distribution list members

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**address** | **String** | Distribution list email address | [required] |
**replace_distribution_list_members_request** | [**ReplaceDistributionListMembersRequest**](ReplaceDistributionListMembersRequest.md) |  | [required] |

### Return type

[**models::ReplaceDistributionListMembers200Response**](replaceDistributionListMembers_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

