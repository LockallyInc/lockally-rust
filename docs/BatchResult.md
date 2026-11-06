# BatchResult

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**index** | Option<**i32**> |  | [optional]
**id** | Option<**uuid::Uuid**> |  | [optional]
**message_id** | Option<**String**> |  | [optional]
**status** | Option<**Status**> | \"suppressed\" means every recipient of that slot was on your suppression list, and it carries no id or message_id. \"delivered\" only appears on a test key: the send was simulated, not transmitted. (enum: queued, scheduled, suppressed, delivered) | [optional]
**error** | Option<**String**> | Present when this message failed; the others are then absent. | [optional]
**warning** | Option<**String**> | Advisory, and NOT a failure. Today the only one is a template variable the template referenced and the request never supplied, which rendered as the empty string. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


