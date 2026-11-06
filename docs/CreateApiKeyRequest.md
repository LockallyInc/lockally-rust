# CreateApiKeyRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**label** | **String** | Free-text identifier shown in the dashboard. | 
**scopes** | **Vec<Scopes>** | Allowed scopes on this key. (enum: tenant:read, tenant:admin, mailboxes:read, mailboxes:write, directory:sync, inboxes:read, inboxes:write, send:read, send:write, templates:read, templates:write, suppressions:read, suppressions:write, webhooks:read, webhooks:write, domains:read, domains:write, migrations:read, migrations:write) | 
**test** | Option<**bool**> | Issue a test key (`lk_test_` prefix). A test key accepts sends, records them and fires a simulated delivery webhook without sending mail, and counts against no limit or allowance.  | [optional][default to false]
**expires_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | Optional. When the key stops authenticating. Omit it for a key that does not expire. Must be in the future: an expiry already past would mint a key that fails its first request.  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


