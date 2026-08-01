# GetAuditSummary200Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**admin_actions_today** | Option<**i32**> |  | [optional]
**recent_logins** | Option<[**Vec<models::AuditEvent>**](AuditEvent.md)> |  | [optional]
**recent_exports** | Option<[**Vec<models::AuditEvent>**](AuditEvent.md)> |  | [optional]
**deleted_mailboxes** | Option<[**Vec<models::AuditEvent>**](AuditEvent.md)> |  | [optional]
**generated_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


