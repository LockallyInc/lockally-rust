# GetCalendarOverview200Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**total_calendars** | Option<**i32**> |  | [optional]
**active_calendars** | Option<**i32**> | Calendars with an event created, edited or held in the last 30 days. | [optional]
**shared_calendars** | Option<**i32**> | Calendars visible to the whole organization. | [optional]
**events_this_month** | Option<**i32**> | Events on every calendar, in the account's own timezone. | [optional]
**upcoming_org_events** | Option<**i32**> | Future events on organization-visible calendars. | [optional]
**bookable_resources** | Option<**i32**> | Resources that are not disabled. | [optional]
**access_granted** | Option<**i32**> | People who own a calendar or are named on one. | [optional]
**access_org_wide** | Option<**i32**> | Everyone who can see an organization calendar; 0 when none exists. | [optional]
**activity** | Option<[**Vec<models::GetCalendarOverview200ResponseActivityInner>**](GetCalendarOverview200ResponseActivityInner.md)> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


