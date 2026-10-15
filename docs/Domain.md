# Domain

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | 
**tenant_id** | **uuid::Uuid** |  | 
**domain** | **String** |  | 
**verification_token** | **String** |  | 
**verified** | **bool** |  | 
**verified_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**dkim_selector** | **String** |  | 
**dkim_public_record** | **String** |  | 
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**records** | Option<[**Vec<models::DnsRecord>**](DNSRecord.md)> | DNS records the tenant must publish under their own DNS. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


