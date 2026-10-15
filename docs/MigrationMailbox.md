# MigrationMailbox

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | 
**migration_id** | **uuid::Uuid** |  | 
**tenant_id** | **uuid::Uuid** |  | 
**source_email** | **String** |  | 
**dest_email** | Option<**String**> |  | [optional]
**dest_mailbox_id** | Option<**uuid::Uuid**> |  | [optional]
**status** | **String** |  | 
**source_message_count** | Option<**i32**> |  | [optional]
**synced_message_count** | **i32** |  | 
**failed_message_count** | **i32** |  | 
**source_size_bytes** | Option<**i64**> |  | [optional]
**synced_size_bytes** | Option<**i64**> |  | [optional]
**last_synced_uid** | Option<**String**> |  | [optional]
**last_synced_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**error_message** | Option<**String**> |  | [optional]
**started_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**completed_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**updated_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


