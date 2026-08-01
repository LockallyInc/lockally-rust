# Migration

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | 
**tenant_id** | **uuid::Uuid** |  | 
**credential_id** | **uuid::Uuid** |  | 
**name** | **String** |  | 
**status** | **Status** |  (enum: draft, discovering, discovered, mapped, pilot_running, pilot_complete, running, staged, cutover_pending, final_syncing, validating, completed, failed, cancelled) | 
**source_provider** | **String** |  | 
**source_summary** | Option<**String**> |  | [optional]
**settings** | Option<[**models::MigrationSettings**](MigrationSettings.md)> |  | [optional]
**error_message** | Option<**String**> |  | [optional]
**started_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**completed_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**mailbox_count** | **i32** |  | 
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**updated_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


