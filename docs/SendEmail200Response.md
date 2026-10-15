# SendEmail200Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | Option<**uuid::Uuid**> | Present on a test-mode send; absent when suppressed. | [optional]
**message_id** | Option<**String**> | RFC 5322 Message-ID. On a test send the domain is test.lockally.com. Absent when suppressed. | [optional]
**status** | **Status** |  (enum: suppressed, delivered) | 
**warning** | Option<**String**> | On a suppressed send, explains that nothing was sent. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


