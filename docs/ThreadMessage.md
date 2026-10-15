# ThreadMessage

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | 
**direction** | **Direction** |  (enum: inbound, outbound) | 
**rfc_message_id** | **String** | The Internet Message-ID | 
**in_reply_to** | Option<**String**> |  | [optional]
**subject** | Option<**String**> |  | [optional]
**from** | **String** |  | 
**to** | **Vec<String>** |  | 
**snippet** | Option<**String**> |  | [optional]
**has_attachments** | **bool** |  | 
**attachments** | Option<**Vec<std::collections::HashMap<String, serde_json::Value>>**> |  | [optional]
**annotations** | Option<**std::collections::HashMap<String, serde_json::Value>**> | Signals computed at ingest | [optional]
**received_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


