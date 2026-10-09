# SendMessage

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**from** | **String** |  | 
**to** | **Vec<String>** |  | 
**cc** | Option<**Vec<String>**> |  | [optional]
**bcc** | Option<**Vec<String>**> |  | [optional]
**subject** | Option<**String**> |  | [optional]
**text** | Option<**String**> |  | [optional]
**html** | Option<**String**> |  | [optional]
**headers** | Option<**std::collections::HashMap<String, String>**> |  | [optional]
**reply_to** | Option<**String**> | Where replies go. Required when `from` has no mailbox behind it. The named form `Acme Support <a@b.com>` is also accepted. | [optional]
**reply_to_name** | Option<**String**> | Display name shown on `Reply-To`. Ignored without `reply_to`. | [optional]
**unsubscribe** | Option<**bool**> |  | [optional]
**template_id** | Option<**uuid::Uuid**> |  | [optional]
**variables** | Option<**std::collections::HashMap<String, String>**> |  | [optional]
**send_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**attachments** | Option<[**Vec<models::V1SendPostRequestAttachmentsInner>**](V1SendPostRequestAttachmentsInner.md)> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


