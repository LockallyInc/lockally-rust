# V1SendPost202Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **uuid::Uuid** | Lockally identifier; use with GET /v1/messages/{id}. | 
**message_id** | **String** | RFC 5322 Message-ID (with angle brackets). | 
**status** | **Status** | \"scheduled\" when send_at is in the future. (enum: queued, scheduled) | 
**warning** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


