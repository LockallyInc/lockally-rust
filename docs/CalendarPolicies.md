# CalendarPolicies

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**tenant_id** | **uuid::Uuid** |  | 
**max_meeting_duration_mins** | Option<**i32**> |  | [optional]
**working_hours_start** | Option<**String**> |  | [optional]
**working_hours_end** | Option<**String**> |  | [optional]
**booking_window_days** | Option<**i32**> |  | [optional]
**recurring_meeting_limit** | Option<**i32**> |  | [optional]
**resource_approval_mode** | Option<**ResourceApprovalMode**> |  (enum: auto_approve, require_approval, restricted) | [optional]
**external_invites_allowed** | Option<**bool**> |  | [optional]
**external_sharing_allowed** | Option<**bool**> |  | [optional]
**public_links_enabled** | Option<**bool**> |  | [optional]
**created_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**updated_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


