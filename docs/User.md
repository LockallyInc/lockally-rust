# User

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | 
**tenant_id** | **uuid::Uuid** |  | 
**email** | **String** |  | 
**first_name** | **String** |  | 
**last_name** | **String** |  | 
**title** | Option<**String**> |  | [optional]
**department** | Option<**String**> |  | [optional]
**status** | **Status** |  (enum: active, suspended, deprovisioned) | 
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**updated_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**mailbox_count** | Option<**i32**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


