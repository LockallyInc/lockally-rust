# CalendarIntegration

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | 
**tenant_id** | **uuid::Uuid** |  | 
**provider** | **Provider** |  (enum: exchange, google_calendar, teams, zoom, erp) | 
**label** | Option<**String**> |  | [optional]
**status** | **Status** |  (enum: connected, disconnected, error, syncing) | 
**last_sync_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**error_message** | Option<**String**> |  | [optional]
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**updated_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


