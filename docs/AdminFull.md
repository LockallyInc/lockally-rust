# AdminFull

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | 
**tenant_id** | **uuid::Uuid** |  | 
**email** | **String** |  | 
**display_name** | Option<**String**> |  | [optional]
**role** | **Role** |  (enum: admin, viewer) | 
**last_login_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**disabled** | **bool** |  | 
**disabled_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**password** | Option<**String**> | Present ONLY on POST response when lockally generated the password. Shown once. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


