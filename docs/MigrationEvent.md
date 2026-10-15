# MigrationEvent

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | 
**migration_id** | **uuid::Uuid** |  | 
**tenant_id** | **uuid::Uuid** |  | 
**mailbox_id** | Option<**uuid::Uuid**> |  | [optional]
**event_type** | **String** |  | 
**actor** | **String** |  | 
**old_status** | Option<**String**> |  | [optional]
**new_status** | Option<**String**> |  | [optional]
**detail** | Option<**String**> |  | [optional]
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


