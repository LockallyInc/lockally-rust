# SendEmailRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**from** | **String** |  | 
**to** | **Vec<String>** |  | 
**cc** | Option<**Vec<String>**> |  | [optional]
**bcc** | Option<**Vec<String>**> |  | [optional]
**subject** | Option<**String**> |  | [optional]
**text** | Option<**String**> | Plain-text body. Required if `html` is absent. | [optional]
**html** | Option<**String**> | HTML body. Required if `text` is absent. | [optional]
**headers** | Option<**std::collections::HashMap<String, String>**> |  | [optional]
**reply_to** | Option<**String**> | Where replies go. REQUIRED when `from` has no mailbox behind it, since a reply there would be delivered nowhere. A `Reply-To` entry in `headers` satisfies the same rule. The named form `Acme Support <a@b.com>` is also accepted. | [optional]
**reply_to_name** | Option<**String**> | Display name shown on `Reply-To`, e.g. `Acme Support`. Ignored without `reply_to`. Encoded and quoted for you, so accents, commas and quotes are all safe. | [optional]
**unsubscribe** | Option<**bool**> | Mark as opt-in/broadcast: skips suppressed recipients and adds a managed one-click List-Unsubscribe header. | [optional]
**template_id** | Option<**uuid::Uuid**> | Render subject/text/html from a stored template (GET /v1/templates). Mutually exclusive with inline subject/text/html. | [optional]
**variables** | Option<**std::collections::HashMap<String, String>**> | Values substituted into the template's {{variable}} placeholders. | [optional]
**send_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> | Schedule delivery for a future RFC3339 time (≤ 30 days out). Omit or past = send now. Cancel with DELETE /v1/messages/{id} while scheduled. | [optional]
**metadata** | Option<**std::collections::HashMap<String, String>**> | Arbitrary key/value you attach to this message and get back on every delivery webhook for it, so a send can be matched to your own records without a lookup table.  **It never leaves Lockally.** A custom entry in `headers` goes out on the wire to the recipient, which is why that is not a substitute: order ids and internal identifiers do not belong in a header the recipient can read.  At most 20 keys, keys at most 64 characters, values at most 512. **Over a limit is refused with a `400`, never truncated**: a silently shortened order id succeeds and then fails to match weeks later.  Not indexed and not filterable.  | [optional]
**tags** | Option<**Vec<String>**> | Labels that group this send for filtering and analytics: campaign, template, environment.  **Lowercased, trimmed and deduplicated on write**, so the grouping does not depend on every caller spelling them identically. `Campaign-X` is stored as `campaign-x`, and either spelling matches it in a filter.  At most 10 per message after deduplication, each at most 32 characters. Over either is a `400` rather than a trimmed list: a send missing the tag it was tagged for is worse than a refusal.  Unlike `metadata`, tags ARE queryable: filter with `GET /v1/messages?tag=` and group with `GET /v1/messages/stats?tag=`.  | [optional]
**track_opens** | Option<**bool**> | Override the account's open-tracking setting for this one send. Omit to inherit it.  Three states matter here: `true`, `false`, and absent. A transactional receipt can set `false` without the account turning tracking off for its marketing.  | [optional]
**track_clicks** | Option<**bool**> | As `track_opens`, for click tracking. Click tracking rewrites `http(s)` links in the **HTML** part only: the plain-text part is never rewritten, because a visible redirect URL is what recipients complain about. A text-only send is therefore not click-tracked.  | [optional]
**attachments** | Option<[**Vec<models::SendEmailRequestAttachmentsInner>**](SendEmailRequestAttachmentsInner.md)> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


