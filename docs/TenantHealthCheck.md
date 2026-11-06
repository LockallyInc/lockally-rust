# TenantHealthCheck

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**key** | **String** | Stable identifier, today one of `domain_verification`, `smtp`, `storage`, `security`. Treat unknown keys as new checks, not errors. | 
**label** | **String** | Human-readable name for display. | 
**status** | **String** | `healthy`, `warning` or `critical`. | 
**detail** | **String** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


