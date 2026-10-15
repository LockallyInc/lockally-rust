# ApiKey

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | 
**tenant_id** | **uuid::Uuid** |  | 
**prefix** | **String** | 8-char public prefix; safe to store and display. | 
**scopes** | **Vec<String>** |  | 
**label** | **String** |  | 
**last_used_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**revoked_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


