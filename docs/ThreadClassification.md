# ThreadClassification

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**thread_id** | **uuid::Uuid** |  | 
**cached** | Option<**bool**> | True when a previous classification was reused. | [optional]
**billed** | Option<**bool**> | True when this call consumed an AI unit. | [optional]
**classification** | Option<[**models::Classification**](Classification.md)> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


