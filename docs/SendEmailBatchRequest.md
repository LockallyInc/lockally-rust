# SendEmailBatchRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**messages** | [**Vec<models::SendMessage>**](SendMessage.md) |  | 
**variables** | Option<**std::collections::HashMap<String, String>**> | Template variables every message in the batch inherits. Each message's own `variables` override these key by key, so shared values are written once and per-recipient ones stay per-recipient.  Without this, a 500-message batch repeats every shared variable 500 times: most of the payload, and 500 places for one of them to differ by a typo.  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


