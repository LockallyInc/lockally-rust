# \MigrationsApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**cancel_migration**](MigrationsApi.md#cancel_migration) | **POST** /v1/migrations/{id}/cancel | Cancel a running migration
[**check_migration_dns**](MigrationsApi.md#check_migration_dns) | **GET** /v1/migrations/{id}/dns-check | Check DNS readiness for cutover
[**create_migration**](MigrationsApi.md#create_migration) | **POST** /v1/migrations | Create a migration
[**create_migration_credential**](MigrationsApi.md#create_migration_credential) | **POST** /v1/migrations/credentials | Store a migration credential
[**delete_migration**](MigrationsApi.md#delete_migration) | **DELETE** /v1/migrations/{id} | Delete a migration
[**delete_migration_credential**](MigrationsApi.md#delete_migration_credential) | **DELETE** /v1/migrations/credentials/{id} | Delete a migration credential
[**delta_sync_migration**](MigrationsApi.md#delta_sync_migration) | **POST** /v1/migrations/{id}/delta-sync | Run a delta sync
[**discover_migration**](MigrationsApi.md#discover_migration) | **POST** /v1/migrations/{id}/discover | Discover source mailboxes
[**final_sync_migration**](MigrationsApi.md#final_sync_migration) | **POST** /v1/migrations/{id}/final-sync | Run the final sync before cutover
[**get_migration**](MigrationsApi.md#get_migration) | **GET** /v1/migrations/{id} | Get a migration
[**get_migration_progress**](MigrationsApi.md#get_migration_progress) | **GET** /v1/migrations/{id}/progress | Get migration progress
[**list_migration_credentials**](MigrationsApi.md#list_migration_credentials) | **GET** /v1/migrations/credentials | List migration credentials
[**list_migration_events**](MigrationsApi.md#list_migration_events) | **GET** /v1/migrations/{id}/events | List migration events
[**list_migration_mailboxes**](MigrationsApi.md#list_migration_mailboxes) | **GET** /v1/migrations/{id}/mailboxes | List migration mailboxes
[**list_migrations**](MigrationsApi.md#list_migrations) | **GET** /v1/migrations | List migrations
[**map_migration**](MigrationsApi.md#map_migration) | **POST** /v1/migrations/{id}/map | Map source to destination mailboxes
[**retry_migration**](MigrationsApi.md#retry_migration) | **POST** /v1/migrations/{id}/retry | Retry a failed or cancelled migration
[**start_migration**](MigrationsApi.md#start_migration) | **POST** /v1/migrations/{id}/start | Start the migration
[**update_migration**](MigrationsApi.md#update_migration) | **PATCH** /v1/migrations/{id} | Update a migration
[**update_migration_mailbox**](MigrationsApi.md#update_migration_mailbox) | **PATCH** /v1/migrations/{id}/mailboxes/{mbxId} | Update a migration mailbox
[**validate_migration**](MigrationsApi.md#validate_migration) | **POST** /v1/migrations/{id}/validate | Validate migrated data



## cancel_migration

> models::DiscoverMigration202Response cancel_migration(id)
Cancel a running migration

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::DiscoverMigration202Response**](discoverMigration_202_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## check_migration_dns

> serde_json::Value check_migration_dns(id)
Check DNS readiness for cutover

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_migration

> models::Migration create_migration(create_migration_request)
Create a migration

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**create_migration_request** | [**CreateMigrationRequest**](CreateMigrationRequest.md) |  | [required] |

### Return type

[**models::Migration**](Migration.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_migration_credential

> models::MigrationCredential create_migration_credential(create_migration_credential_request)
Store a migration credential

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**create_migration_credential_request** | [**CreateMigrationCredentialRequest**](CreateMigrationCredentialRequest.md) |  | [required] |

### Return type

[**models::MigrationCredential**](MigrationCredential.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_migration

> delete_migration(id)
Delete a migration

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


## delete_migration_credential

> delete_migration_credential(id)
Delete a migration credential

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


## delta_sync_migration

> models::StartMigration202Response delta_sync_migration(id)
Run a delta sync

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::StartMigration202Response**](startMigration_202_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## discover_migration

> models::DiscoverMigration202Response discover_migration(id)
Discover source mailboxes

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::DiscoverMigration202Response**](discoverMigration_202_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## final_sync_migration

> models::StartMigration202Response final_sync_migration(id)
Run the final sync before cutover

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::StartMigration202Response**](startMigration_202_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_migration

> models::Migration get_migration(id)
Get a migration

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::Migration**](Migration.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_migration_progress

> models::MigrationProgress get_migration_progress(id)
Get migration progress

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::MigrationProgress**](MigrationProgress.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_migration_credentials

> models::ListMigrationCredentials200Response list_migration_credentials()
List migration credentials

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::ListMigrationCredentials200Response**](listMigrationCredentials_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_migration_events

> models::ListMigrationEvents200Response list_migration_events(id)
List migration events

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::ListMigrationEvents200Response**](listMigrationEvents_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_migration_mailboxes

> models::ListMigrationMailboxes200Response list_migration_mailboxes(id)
List migration mailboxes

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::ListMigrationMailboxes200Response**](listMigrationMailboxes_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_migrations

> models::ListMigrations200Response list_migrations()
List migrations

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::ListMigrations200Response**](listMigrations_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## map_migration

> models::DiscoverMigration202Response map_migration(id, map_migration_request)
Map source to destination mailboxes

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |
**map_migration_request** | [**MapMigrationRequest**](MapMigrationRequest.md) |  | [required] |

### Return type

[**models::DiscoverMigration202Response**](discoverMigration_202_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## retry_migration

> models::DiscoverMigration202Response retry_migration(id)
Retry a failed or cancelled migration

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::DiscoverMigration202Response**](discoverMigration_202_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## start_migration

> models::StartMigration202Response start_migration(id)
Start the migration

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::StartMigration202Response**](startMigration_202_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_migration

> models::Migration update_migration(id, update_migration_request)
Update a migration

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |
**update_migration_request** | [**UpdateMigrationRequest**](UpdateMigrationRequest.md) |  | [required] |

### Return type

[**models::Migration**](Migration.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_migration_mailbox

> update_migration_mailbox(id, mbx_id, update_migration_mailbox_request)
Update a migration mailbox

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |
**mbx_id** | **uuid::Uuid** |  | [required] |
**update_migration_mailbox_request** | [**UpdateMigrationMailboxRequest**](UpdateMigrationMailboxRequest.md) |  | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## validate_migration

> models::StartMigration202Response validate_migration(id)
Validate migrated data

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::StartMigration202Response**](startMigration_202_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

