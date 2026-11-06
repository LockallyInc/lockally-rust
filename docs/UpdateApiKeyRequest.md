# UpdateApiKeyRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**label** | Option<**String**> | Free-text identifier shown in the dashboard. | [optional]
**scopes** | Option<**Vec<String>**> | Replaces the key's scopes entirely. | [optional]
**expires_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | A future timestamp to set an expiry, or null to remove one. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


