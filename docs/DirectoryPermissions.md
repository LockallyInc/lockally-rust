# DirectoryPermissions

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**tenant_id** | **uuid::Uuid** |  | 
**contact_view_access** | **ContactViewAccess** |  (enum: all_users, same_department, admins_only) | 
**contact_edit_access** | **ContactEditAccess** |  (enum: all_users, admins_only) | 
**list_manage_access** | **ListManageAccess** |  (enum: all_users, list_owners, admins_only) | 
**external_sharing** | **ExternalSharing** |  (enum: allowed, restricted, disabled) | 
**created_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]
**updated_at** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


