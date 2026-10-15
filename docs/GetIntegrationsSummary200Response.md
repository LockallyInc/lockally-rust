# GetIntegrationsSummary200Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**api_requests_today** | Option<**i32**> |  | [optional]
**active_api_keys** | Option<**i32**> |  | [optional]
**api_keys** | Option<[**Vec<models::GetIntegrationsSummary200ResponseApiKeysInner>**](GetIntegrationsSummary200ResponseApiKeysInner.md)> |  | [optional]
**webhook_failures** | Option<**i32**> |  | [optional]
**webhooks_total** | Option<**i32**> |  | [optional]
**webhooks** | Option<[**Vec<models::GetIntegrationsSummary200ResponseWebhooksInner>**](GetIntegrationsSummary200ResponseWebhooksInner.md)> |  | [optional]
**generated_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


