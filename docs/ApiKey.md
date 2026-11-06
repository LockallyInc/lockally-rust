# ApiKey

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | 
**tenant_id** | **uuid::Uuid** |  | 
**prefix** | **String** | 8-char public prefix; safe to store and display. | 
**scopes** | **Vec<String>** |  | 
**label** | **String** |  | 
**last_used_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**revoked_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**test** | Option<**bool**> | True for an lk_test_* key: the whole request path runs but a send never reaches the mail server and nothing counts against the account. | [optional]
**expires_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | When the key stops authenticating. Null means it does not expire, which is how every key behaved before expiry existed. Enforced at authentication, so the key fails the first request after this moment rather than whenever a sweep runs.  | [optional]
**rotated_to** | Option<**uuid::Uuid**> | The successor issued by `POST /v1/api-keys/{id}/rotate`. Set on the PREDECESSOR, so you can see which key replaced this one while both still work through the overlap window.  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


