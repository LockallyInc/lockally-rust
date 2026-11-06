# Contact

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | 
**tenant_id** | **uuid::Uuid** |  | 
**name** | **String** |  | 
**email** | **String** |  | 
**phone** | Option<**String**> |  | [optional]
**company** | Option<**String**> |  | [optional]
**notes** | Option<**String**> |  | [optional]
**contact_type** | **ContactType** |  (enum: internal, external) | 
**source** | Option<**String**> |  | [optional]
**department** | Option<**String**> |  | [optional]
**role** | Option<**String**> |  | [optional]
**status** | **String** |  | 
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**updated_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**external_system** | Option<**String**> | The system that owns this contact's external id. Absent on contacts made by hand. | [optional]
**external_id** | Option<**String**> | The contact's id in `external_system`. Absent on contacts made by hand. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


