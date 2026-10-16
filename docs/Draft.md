# Draft

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | 
**mailbox_id** | **uuid::Uuid** |  | 
**mailbox** | Option<**String**> |  | [optional]
**thread_id** | Option<**uuid::Uuid**> |  | [optional]
**to** | **Vec<String>** |  | 
**cc** | Option<**Vec<String>**> |  | [optional]
**subject** | Option<**String**> |  | [optional]
**body_text** | Option<**String**> |  | [optional]
**status** | **Status** |  (enum: pending_approval, sent, rejected, cancelled) | 
**policy_flags** | [**models::PolicyFlags**](PolicyFlags.md) |  | 
**reviewed_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**sent_message_id** | Option<**uuid::Uuid**> |  | [optional]
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**updated_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


