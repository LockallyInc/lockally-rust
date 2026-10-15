# Mailbox

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | 
**tenant_id** | **uuid::Uuid** |  | 
**domain_id** | **uuid::Uuid** |  | 
**email** | **String** |  | 
**quota_bytes** | **i64** |  | 
**disabled** | **bool** |  | 
**disabled_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**soft_deleted_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**hard_delete_after** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**password** | Option<**String**> | ONLY present on POST response when lockally generated the password. Shown once. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


