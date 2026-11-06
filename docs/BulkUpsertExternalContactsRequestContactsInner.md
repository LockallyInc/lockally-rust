# BulkUpsertExternalContactsRequestContactsInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**email** | **String** |  | 
**name** | Option<**String**> | Defaults to the email address when empty. | [optional]
**phone** | Option<**String**> |  | [optional]
**company** | Option<**String**> |  | [optional]
**notes** | Option<**String**> |  | [optional]
**contact_type** | Option<**ContactType**> |  (enum: internal, external) | [optional][default to External]
**department** | Option<**String**> |  | [optional]
**role** | Option<**String**> |  | [optional]
**status** | Option<**Status**> |  (enum: active, disabled) | [optional][default to Active]
**external_id** | **String** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


