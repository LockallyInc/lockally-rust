# BillingStatus

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**plan** | **String** |  | 
**display_name** | **String** |  | 
**mode** | **Mode** |  (enum: api, business, both) | 
**rate_cap_per_min** | **i32** |  | 
**monthly_included_sends** | **i32** |  | 
**msgs_this_period** | **i32** |  | 
**status** | **Status** |  (enum: active, suspended) | 
**price_naira_per_seat** | **i32** |  | 
**subscribed_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**current_period_end** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**send_units_balance** | **i32** |  | 
**send_units_next_expiry** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**unit_bundles** | [**Vec<models::UnitBundle>**](UnitBundle.md) |  | 
**catalog** | [**Vec<models::PlanCatalogEntry>**](PlanCatalogEntry.md) |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


