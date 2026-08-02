# Calendar

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | 
**tenant_id** | **uuid::Uuid** |  | 
**name** | **String** |  | 
**color** | Option<**String**> |  | [optional]
**owner_email** | Option<**String**> |  | [optional]
**description** | Option<**String**> |  | [optional]
**visibility** | **Visibility** |  (enum: private, tenant) | 
**feed_url** | Option<**String**> |  | [optional]
**event_count** | Option<**i32**> |  | [optional]
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**updated_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


