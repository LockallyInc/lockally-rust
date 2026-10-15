# MessageDetail

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | 
**tenant_id** | **uuid::Uuid** |  | 
**message_id** | **String** | RFC 5322 Message-ID header, including angle brackets. | 
**sender** | **String** |  | 
**recipients** | **Vec<String>** |  | 
**subject** | Option<**String**> |  | [optional]
**status** | **Status** |  (enum: queued, sending, delivered, bounced, deferred, complaint) | 
**queued_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**updated_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**bounce_reason** | Option<**String**> |  | [optional]
**size_bytes** | Option<**i32**> |  | [optional]
**from** | Option<**String**> |  | [optional]
**to** | Option<**Vec<String>**> |  | [optional]
**cc** | Option<**Vec<String>**> |  | [optional]
**bcc** | Option<**Vec<String>**> |  | [optional]
**text** | Option<**String**> |  | [optional]
**html** | Option<**String**> |  | [optional]
**headers** | Option<**std::collections::HashMap<String, String>**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


