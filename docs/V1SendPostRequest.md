# V1SendPostRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**from** | **String** |  | 
**to** | **Vec<String>** |  | 
**cc** | Option<**Vec<String>**> |  | [optional]
**bcc** | Option<**Vec<String>**> |  | [optional]
**subject** | Option<**String**> |  | [optional]
**text** | Option<**String**> | Plain-text body. Required if `html` is absent. | [optional]
**html** | Option<**String**> | HTML body. Required if `text` is absent. | [optional]
**headers** | Option<**std::collections::HashMap<String, String>**> |  | [optional]
**unsubscribe** | Option<**bool**> | Mark as opt-in/broadcast: skips suppressed recipients and adds a managed one-click List-Unsubscribe header. | [optional]
**template_id** | Option<**uuid::Uuid**> | Render subject/text/html from a stored template (GET /v1/templates). Mutually exclusive with inline subject/text/html. | [optional]
**variables** | Option<**std::collections::HashMap<String, String>**> | Values substituted into the template's {{variable}} placeholders. | [optional]
**send_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | Schedule delivery for a future RFC3339 time (≤ 30 days out). Omit or past = send now. Cancel with DELETE /v1/messages/{id} while scheduled. | [optional]
**attachments** | Option<[**Vec<models::V1SendPostRequestAttachmentsInner>**](V1SendPostRequestAttachmentsInner.md)> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


