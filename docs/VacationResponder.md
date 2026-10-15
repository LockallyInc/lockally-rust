# VacationResponder

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**mailbox_email** | **String** |  | 
**enabled** | **bool** |  | 
**params** | [**models::VacationParams**](VacationParams.md) |  | 
**script** | **String** | Pre-rendered Sieve script (RFC 5230). | 
**synced_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | Null = stored on lockally but not yet pushed to the mail server. | [optional]
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**updated_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


