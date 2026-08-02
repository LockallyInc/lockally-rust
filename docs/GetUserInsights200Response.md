# GetUserInsights200Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**recently_added** | Option<[**Vec<models::UserEvent>**](UserEvent.md)> |  | [optional]
**recently_suspended** | Option<[**Vec<models::UserEvent>**](UserEvent.md)> |  | [optional]
**inactive_30d** | Option<[**Vec<models::UserEvent>**](UserEvent.md)> |  | [optional]
**seats_used** | Option<**i32**> |  | [optional]
**seats_alloc** | Option<**i32**> |  | [optional]
**seats_capped** | Option<**bool**> | True only on tiers with a hard seat cap (Free, Founder). On unlimited/per-seat tiers seats_alloc merely tracks the live mailbox count, so seats_used == seats_alloc is normal and must not be read as 'at capacity'. | [optional]
**generated_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


