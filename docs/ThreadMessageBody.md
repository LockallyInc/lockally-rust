# ThreadMessageBody

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**thread_id** | **uuid::Uuid** |  | 
**mailbox** | **String** |  | 
**message** | [**models::ThreadMessage**](ThreadMessage.md) |  | 
**body** | Option<[**models::ThreadMessageBodyBody**](ThreadMessageBodyBody.md)> |  | [optional]
**body_unavailable** | Option<**String**> | Present instead of body when the message could not be located in the mailbox. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


