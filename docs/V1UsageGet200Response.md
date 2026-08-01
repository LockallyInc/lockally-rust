# V1UsageGet200Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**mailboxes_active** | **i32** | Mailboxes that are neither disabled nor soft-deleted. | 
**mailboxes_total** | Option<**i32**> | All mailboxes for this tenant, including disabled/soft-deleted. | [optional]
**domains_verified** | Option<**i32**> | Domains that have passed DNS verification. | [optional]
**domains_total** | Option<**i32**> |  | [optional]
**messages_sent_last_60s** | Option<**i32**> | Sends in the 60-second window ending now. Used by the rate-cap check. | [optional]
**messages_sent_today_utc** | Option<**i32**> | Sends since 00:00 UTC. Compared against `daily_msg_quota`. | [optional]
**messages_sent_last_30d** | Option<**i32**> | Rolling 30-day send count (not calendar month). | [optional]
**bytes_stored** | Option<**i64**> | Lifetime sum of `messages.size_bytes` for this tenant. | [optional]
**rate_cap_per_min** | Option<**i32**> | Per-tenant outbound rate cap (sends per minute). | [optional]
**daily_msg_quota** | Option<**i32**> | Per-tenant daily send quota (UTC day boundary). | [optional]
**webhooks_total** | Option<**i32**> |  | [optional]
**webhooks_paused** | Option<**i32**> | Webhook subscriptions auto-paused after 50 consecutive failures (LT2). | [optional]
**generated_at** | **chrono::DateTime<chrono::FixedOffset>** | When this snapshot was generated, RFC 3339 UTC. | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


