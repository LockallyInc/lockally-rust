# MigrationProgress

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**migration_id** | **uuid::Uuid** |  | 
**status** | **String** |  | 
**total_mailboxes** | **i32** |  | 
**completed_mailboxes** | **i32** |  | 
**failed_mailboxes** | **i32** |  | 
**total_messages** | **i32** |  | 
**synced_messages** | **i32** |  | 
**failed_messages** | **i32** |  | 
**percent_complete** | **f64** |  | 
**mailboxes** | [**Vec<models::MigrationProgressMailboxesInner>**](MigrationProgressMailboxesInner.md) |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


