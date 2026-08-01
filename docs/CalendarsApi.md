# \CalendarsApi

All URIs are relative to *https://api.lockally.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_calendar_member**](CalendarsApi.md#add_calendar_member) | **POST** /v1/calendars/{id}/members | Add a member to a calendar
[**create_calendar**](CalendarsApi.md#create_calendar) | **POST** /v1/calendars | Create a calendar
[**create_calendar_event**](CalendarsApi.md#create_calendar_event) | **POST** /v1/calendars/{id}/events | Create an event in a calendar
[**create_calendar_integration**](CalendarsApi.md#create_calendar_integration) | **POST** /v1/calendar-integrations | Create a calendar integration
[**delete_calendar**](CalendarsApi.md#delete_calendar) | **DELETE** /v1/calendars/{id} | Delete a calendar
[**delete_calendar_event**](CalendarsApi.md#delete_calendar_event) | **DELETE** /v1/calendars/{id}/events/{eventId} | Delete a calendar event
[**delete_calendar_integration**](CalendarsApi.md#delete_calendar_integration) | **DELETE** /v1/calendar-integrations/{id} | Delete a calendar integration
[**get_calendar**](CalendarsApi.md#get_calendar) | **GET** /v1/calendars/{id} | Get a calendar
[**get_calendar_policies**](CalendarsApi.md#get_calendar_policies) | **GET** /v1/calendar-policies | Get calendar policies
[**get_calendar_security**](CalendarsApi.md#get_calendar_security) | **GET** /v1/calendar-security | Get calendar security overview
[**list_calendar_events**](CalendarsApi.md#list_calendar_events) | **GET** /v1/calendars/{id}/events | List events in a calendar
[**list_calendar_integrations**](CalendarsApi.md#list_calendar_integrations) | **GET** /v1/calendar-integrations | List calendar integrations
[**list_calendar_members**](CalendarsApi.md#list_calendar_members) | **GET** /v1/calendars/{id}/members | List calendar members
[**list_calendars**](CalendarsApi.md#list_calendars) | **GET** /v1/calendars | List calendars
[**remove_calendar_member**](CalendarsApi.md#remove_calendar_member) | **DELETE** /v1/calendars/{id}/members/{memberId} | Remove a member from a calendar
[**sync_calendar_integration**](CalendarsApi.md#sync_calendar_integration) | **POST** /v1/calendar-integrations/{id}/sync | Trigger sync for a calendar integration
[**update_calendar**](CalendarsApi.md#update_calendar) | **PATCH** /v1/calendars/{id} | Update a calendar
[**update_calendar_event**](CalendarsApi.md#update_calendar_event) | **PATCH** /v1/calendars/{id}/events/{eventId} | Update a calendar event
[**update_calendar_integration**](CalendarsApi.md#update_calendar_integration) | **PATCH** /v1/calendar-integrations/{id} | Update a calendar integration
[**update_calendar_member**](CalendarsApi.md#update_calendar_member) | **PATCH** /v1/calendars/{id}/members/{memberId} | Update a calendar member's role
[**update_calendar_policies**](CalendarsApi.md#update_calendar_policies) | **PATCH** /v1/calendar-policies | Update calendar policies



## add_calendar_member

> models::CalendarMember add_calendar_member(id, add_calendar_member_request)
Add a member to a calendar

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |
**add_calendar_member_request** | [**AddCalendarMemberRequest**](AddCalendarMemberRequest.md) |  | [required] |

### Return type

[**models::CalendarMember**](CalendarMember.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_calendar

> models::Calendar create_calendar(create_calendar_request)
Create a calendar

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**create_calendar_request** | [**CreateCalendarRequest**](CreateCalendarRequest.md) |  | [required] |

### Return type

[**models::Calendar**](Calendar.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_calendar_event

> models::CalendarEvent create_calendar_event(id, create_calendar_event_request)
Create an event in a calendar

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |
**create_calendar_event_request** | [**CreateCalendarEventRequest**](CreateCalendarEventRequest.md) |  | [required] |

### Return type

[**models::CalendarEvent**](CalendarEvent.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_calendar_integration

> models::CalendarIntegration create_calendar_integration(create_calendar_integration_request)
Create a calendar integration

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**create_calendar_integration_request** | [**CreateCalendarIntegrationRequest**](CreateCalendarIntegrationRequest.md) |  | [required] |

### Return type

[**models::CalendarIntegration**](CalendarIntegration.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_calendar

> delete_calendar(id)
Delete a calendar

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_calendar_event

> delete_calendar_event(id, event_id)
Delete a calendar event

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |
**event_id** | **uuid::Uuid** |  | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_calendar_integration

> delete_calendar_integration(id)
Delete a calendar integration

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_calendar

> models::Calendar get_calendar(id)
Get a calendar

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::Calendar**](Calendar.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_calendar_policies

> models::CalendarPolicies get_calendar_policies()
Get calendar policies

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::CalendarPolicies**](CalendarPolicies.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_calendar_security

> models::GetCalendarSecurity200Response get_calendar_security()
Get calendar security overview

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::GetCalendarSecurity200Response**](getCalendarSecurity_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_calendar_events

> models::ListCalendarEvents200Response list_calendar_events(id, from, to)
List events in a calendar

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |
**from** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  |  |
**to** | Option<**chrono::DateTime<chrono::FixedOffset>**> |  |  |

### Return type

[**models::ListCalendarEvents200Response**](listCalendarEvents_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_calendar_integrations

> models::ListCalendarIntegrations200Response list_calendar_integrations()
List calendar integrations

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::ListCalendarIntegrations200Response**](listCalendarIntegrations_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_calendar_members

> models::ListCalendarMembers200Response list_calendar_members(id)
List calendar members

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::ListCalendarMembers200Response**](listCalendarMembers_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_calendars

> models::ListCalendars200Response list_calendars()
List calendars

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::ListCalendars200Response**](listCalendars_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## remove_calendar_member

> remove_calendar_member(id, member_id)
Remove a member from a calendar

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |
**member_id** | **uuid::Uuid** |  | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## sync_calendar_integration

> models::CalendarIntegration sync_calendar_integration(id)
Trigger sync for a calendar integration

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |

### Return type

[**models::CalendarIntegration**](CalendarIntegration.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_calendar

> models::Calendar update_calendar(id, update_calendar_request)
Update a calendar

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |
**update_calendar_request** | [**UpdateCalendarRequest**](UpdateCalendarRequest.md) |  | [required] |

### Return type

[**models::Calendar**](Calendar.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_calendar_event

> models::CalendarEvent update_calendar_event(id, event_id, update_calendar_event_request)
Update a calendar event

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |
**event_id** | **uuid::Uuid** |  | [required] |
**update_calendar_event_request** | [**UpdateCalendarEventRequest**](UpdateCalendarEventRequest.md) |  | [required] |

### Return type

[**models::CalendarEvent**](CalendarEvent.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_calendar_integration

> models::CalendarIntegration update_calendar_integration(id, update_calendar_integration_request)
Update a calendar integration

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |
**update_calendar_integration_request** | [**UpdateCalendarIntegrationRequest**](UpdateCalendarIntegrationRequest.md) |  | [required] |

### Return type

[**models::CalendarIntegration**](CalendarIntegration.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_calendar_member

> models::CalendarMember update_calendar_member(id, member_id, update_calendar_member_request)
Update a calendar member's role

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**id** | **uuid::Uuid** |  | [required] |
**member_id** | **uuid::Uuid** |  | [required] |
**update_calendar_member_request** | [**UpdateCalendarMemberRequest**](UpdateCalendarMemberRequest.md) |  | [required] |

### Return type

[**models::CalendarMember**](CalendarMember.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_calendar_policies

> models::CalendarPolicies update_calendar_policies(update_calendar_policies_request)
Update calendar policies

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**update_calendar_policies_request** | [**UpdateCalendarPoliciesRequest**](UpdateCalendarPoliciesRequest.md) |  | [required] |

### Return type

[**models::CalendarPolicies**](CalendarPolicies.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

