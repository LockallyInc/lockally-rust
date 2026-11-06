# GetEncryptionKey200Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | Option<**uuid::Uuid**> |  | [optional]
**email** | Option<**String**> |  | [optional]
**public_key** | Option<**String**> |  | [optional]
**encrypted_private_key** | Option<**String**> |  | [optional]
**kdf_params** | Option<**serde_json::Value**> |  | [optional]
**version** | Option<**i32**> |  | [optional]
**created_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**rotated_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**has_recovery** | Option<**bool**> |  | [optional]
**recovery_set_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**recovery_blob** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


