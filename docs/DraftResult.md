# DraftResult

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**draft_id** | **uuid::Uuid** |  | 
**status** | **Status** |  (enum: pending_approval, sent) | 
**policy_flags** | [**models::PolicyFlags**](PolicyFlags.md) |  | 
**thread_id** | Option<**uuid::Uuid**> |  | [optional]
**sent** | Option<[**models::AgentSendResult**](AgentSendResult.md)> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


