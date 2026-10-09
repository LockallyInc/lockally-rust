# ReturnPath

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**status** | **Status** |  (enum: false, pending, active) | 
**host** | **String** |  | 
**records** | [**Vec<models::DnsRecord>**](DNSRecord.md) |  | 
**check** | Option<[**models::ReturnPathCheck**](ReturnPathCheck.md)> |  | [optional]
**requested_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**verified_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


