# Calendar

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | 
**tenant_id** | **uuid::Uuid** |  | 
**name** | **String** |  | 
**color** | Option<**String**> |  | [optional]
**owner_email** | Option<**String**> |  | [optional]
**description** | Option<**String**> |  | [optional]
**calendar_type** | Option<**CalendarType**> | What the calendar is for. Separate from visibility, which is who may see it: a team calendar can be open to everyone and a department one restricted to named people. \"personal\" is a person's own and is not listed in the console's management table.  (enum: personal, organization, department, team, shared) | [optional]
**owner_unit** | Option<**String**> | The owning department or office. Empty on a personal calendar, which is owned by owner_email. | [optional]
**visibility** | **Visibility** |  (enum: private, tenant, department) | 
**access_department** | Option<**String**> | Which department may see it, when visibility is \"department\". Matched against the department recorded on a user, so access follows a person between departments with no membership list to maintain.  | [optional]
**status** | Option<**Status**> | Archived keeps the calendar, its events and its feed, and stops it taking new events. (enum: active, archived) | [optional]
**feed_url** | Option<**String**> |  | [optional]
**event_count** | Option<**i32**> |  | [optional]
**created_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 
**updated_at** | **chrono::DateTime<chrono::FixedOffset>** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


