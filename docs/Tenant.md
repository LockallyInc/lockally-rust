# Tenant

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | 
**slug** | **String** |  | 
**display_name** | **String** |  | 
**status** | **Status** |  (enum: active, suspended, closing, closed) | 
**plan** | **String** |  | 
**rate_cap_per_min** | **i32** | Per-tenant share of the per-VPS 5/min outbound cap (L6). | 
**daily_msg_quota** | **i32** |  | 
**admin_email** | **String** |  | 
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**suspended_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**closed_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**hard_delete_after** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


