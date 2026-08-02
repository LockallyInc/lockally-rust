# BatchResult

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**index** | Option<**i32**> |  | [optional]
**id** | Option<**uuid::Uuid**> |  | [optional]
**message_id** | Option<**String**> |  | [optional]
**status** | Option<**Status**> |  (enum: queued, scheduled, suppressed) | [optional]
**error** | Option<**String**> | Present when this message failed; the others are then absent. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


