# Webhook

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | 
**tenant_id** | **uuid::Uuid** |  | 
**url** | **String** |  | 
**events** | **Vec<String>** |  | 
**paused** | **bool** |  | 
**paused_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**last_success_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**last_failure_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**consecutive_failures** | **i32** |  | 
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**signing_secret** | Option<**String**> | Hex-encoded HMAC-SHA256 key. Present ONLY on POST response. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


