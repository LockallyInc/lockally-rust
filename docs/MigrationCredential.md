# MigrationCredential

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | 
**tenant_id** | **uuid::Uuid** |  | 
**provider** | **Provider** |  (enum: imap, google, microsoft, generic) | 
**encryption_key_id** | Option<**String**> |  | [optional]
**label** | Option<**String**> |  | [optional]
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**updated_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


