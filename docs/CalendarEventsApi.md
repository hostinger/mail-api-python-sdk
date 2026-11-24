# hostinger_mail_api.CalendarEventsApi

All URIs are relative to *https://api.mail.hostinger.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_calendar_event**](CalendarEventsApi.md#create_calendar_event) | **POST** /api/v1/mailboxes/{mailboxResourceId}/calendars/{calendarUuid}/events | Create calendar event
[**delete_calendar_event**](CalendarEventsApi.md#delete_calendar_event) | **DELETE** /api/v1/mailboxes/{mailboxResourceId}/calendars/{calendarUuid}/events/{eventUuid} | Delete calendar event
[**get_calendar_event**](CalendarEventsApi.md#get_calendar_event) | **GET** /api/v1/mailboxes/{mailboxResourceId}/calendars/{calendarUuid}/events/{eventUuid} | Get calendar event
[**list_calendar_events**](CalendarEventsApi.md#list_calendar_events) | **GET** /api/v1/mailboxes/{mailboxResourceId}/calendars/{calendarUuid}/events | List calendar events
[**reply_to_calendar_event**](CalendarEventsApi.md#reply_to_calendar_event) | **POST** /api/v1/mailboxes/{mailboxResourceId}/calendars/{calendarUuid}/events/{eventUuid}/reply | Reply to calendar event
[**reschedule_calendar_event**](CalendarEventsApi.md#reschedule_calendar_event) | **PUT** /api/v1/mailboxes/{mailboxResourceId}/calendars/{calendarUuid}/events/{eventUuid}/reschedule | Reschedule calendar event
[**update_calendar_event**](CalendarEventsApi.md#update_calendar_event) | **PUT** /api/v1/mailboxes/{mailboxResourceId}/calendars/{calendarUuid}/events/{eventUuid} | Update calendar event


# **create_calendar_event**
> V1CalendarEventsResource create_calendar_event(mailbox_resource_id, calendar_uuid, v1_calendar_events_create_request)

Create calendar event

Create an event in one calendar of the mailbox. `calendarUuid` comes from `listCalendars`: use the calendar with `default` true unless another one is named. A calendar the mailbox can only read is rejected with `403` and code `ERR_EVENT_NOT_EDITABLE`.
The mailbox becomes the organizer and every address in `attendees` immediately receives an email invitation, which cannot be recalled. Without attendees no email is sent.
A timed event needs `allDay` false, `start`, `end` and `timeZone`. An all-day event needs `allDay` true and a `start` date; `end` is optional. Set `recurrenceRule` for a repeating event and `reminder` for an alarm.
Returns the created event. Its `uuid` is the `eventUuid` for `getCalendarEvent`, `updateCalendarEvent`, `rescheduleCalendarEvent` and `deleteCalendarEvent`.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_calendar_events_create_request import V1CalendarEventsCreateRequest
from hostinger_mail_api.models.v1_calendar_events_resource import V1CalendarEventsResource
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.CalendarEventsApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    calendar_uuid = '42c370e3-48ae-4286-90c5-d952f28c67cc' # str | Calendar identifier: the `uuid` of a calendar returned by `listCalendars`, or the `calendarUuid` of an event returned by `listCalendarEvents`.
    v1_calendar_events_create_request = hostinger_mail_api.V1CalendarEventsCreateRequest() # V1CalendarEventsCreateRequest | 

    try:
        # Create calendar event
        api_response = api_instance.create_calendar_event(mailbox_resource_id, calendar_uuid, v1_calendar_events_create_request)
        print("The response of CalendarEventsApi->create_calendar_event:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling CalendarEventsApi->create_calendar_event: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **calendar_uuid** | **str**| Calendar identifier: the &#x60;uuid&#x60; of a calendar returned by &#x60;listCalendars&#x60;, or the &#x60;calendarUuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. | 
 **v1_calendar_events_create_request** | [**V1CalendarEventsCreateRequest**](V1CalendarEventsCreateRequest.md)|  | 

### Return type

[**V1CalendarEventsResource**](V1CalendarEventsResource.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | Event created. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**404** | Resource not found. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_calendar_event**
> delete_calendar_event(mailbox_resource_id, calendar_uuid, event_uuid, scope=scope, recurrence_id=recurrence_id, notify_attendees=notify_attendees, if_match=if_match)

Delete calendar event

Delete an event, one occurrence of a recurring event, or a recurring event from one occurrence on. This cannot be undone. `calendarUuid` and `eventUuid` come from `listCalendarEvents`.
For a one-off event omit `scope` and `recurrenceId`. For a recurring event, `scope` `this` removes only the occurrence at `recurrenceId`, `future` removes it and every later one, `all` (the default) deletes the whole series.
An event with `editable` true can be deleted with any scope, and its attendees receive a cancellation or the updated series by email. An invitation from someone else on the own calendar of the mailbox can be deleted with `all` or `this`: the organizer receives a decline for the removed occurrences. Any other event is rejected with `403` and code `ERR_EVENT_NOT_EDITABLE`. `notifyAttendees` false deletes without sending any email.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.CalendarEventsApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    calendar_uuid = '42c370e3-48ae-4286-90c5-d952f28c67cc' # str | Calendar identifier: the `uuid` of a calendar returned by `listCalendars`, or the `calendarUuid` of an event returned by `listCalendarEvents`.
    event_uuid = 'a1b2c3d4-e5f6-7890-abcd-ef1234567890' # str | Event identifier: the `uuid` of an event returned by `listCalendarEvents`. Every occurrence of a recurring event has the same uuid; `recurrenceId` picks one occurrence.
    scope = 'this' # str | For a recurring event: `this` removes the occurrence at `recurrenceId`, `future` removes it and every later one, `all` deletes the whole series. Omitted means `all`. Required when `recurrenceId` is sent. (optional)
    recurrence_id = '2026-10-05T07:00:00.000000Z' # datetime | `recurrenceId` of one occurrence, copied unchanged from a `listCalendarEvents` item. Required when `scope` is `this` or `future`. A value that matches no occurrence, or any value on a one-off event, returns `404`. (optional)
    notify_attendees = true # str | `false` deletes without emailing attendees a cancellation or update, or the organizer a decline. Omitted means `true`. (optional) (default to true)
    if_match = '3c9f1a2b8e04' # str | Optional `etag` from `getCalendarEvent`. When the event changed since that call, nothing is deleted and the request fails with `412`: fetch the event again and retry. Omit it to apply the request to the current version. (optional)

    try:
        # Delete calendar event
        api_instance.delete_calendar_event(mailbox_resource_id, calendar_uuid, event_uuid, scope=scope, recurrence_id=recurrence_id, notify_attendees=notify_attendees, if_match=if_match)
    except Exception as e:
        print("Exception when calling CalendarEventsApi->delete_calendar_event: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **calendar_uuid** | **str**| Calendar identifier: the &#x60;uuid&#x60; of a calendar returned by &#x60;listCalendars&#x60;, or the &#x60;calendarUuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. | 
 **event_uuid** | **str**| Event identifier: the &#x60;uuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. Every occurrence of a recurring event has the same uuid; &#x60;recurrenceId&#x60; picks one occurrence. | 
 **scope** | **str**| For a recurring event: &#x60;this&#x60; removes the occurrence at &#x60;recurrenceId&#x60;, &#x60;future&#x60; removes it and every later one, &#x60;all&#x60; deletes the whole series. Omitted means &#x60;all&#x60;. Required when &#x60;recurrenceId&#x60; is sent. | [optional] 
 **recurrence_id** | **datetime**| &#x60;recurrenceId&#x60; of one occurrence, copied unchanged from a &#x60;listCalendarEvents&#x60; item. Required when &#x60;scope&#x60; is &#x60;this&#x60; or &#x60;future&#x60;. A value that matches no occurrence, or any value on a one-off event, returns &#x60;404&#x60;. | [optional] 
 **notify_attendees** | **str**| &#x60;false&#x60; deletes without emailing attendees a cancellation or update, or the organizer a decline. Omitted means &#x60;true&#x60;. | [optional] [default to true]
 **if_match** | **str**| Optional &#x60;etag&#x60; from &#x60;getCalendarEvent&#x60;. When the event changed since that call, nothing is deleted and the request fails with &#x60;412&#x60;: fetch the event again and retry. Omit it to apply the request to the current version. | [optional] 

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**204** | Event deleted. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**404** | Resource not found. |  -  |
**412** | The resource changed since the etag sent in &#x60;If-Match&#x60; was read. Nothing was changed: fetch the resource again and retry. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_calendar_event**
> V1CalendarEventsResource get_calendar_event(mailbox_resource_id, calendar_uuid, event_uuid, recurrence_id=recurrence_id)

Get calendar event

Retrieve the full details of one event: title, times, description, location, meeting link, recurrence rule, reminder, organizer, attendees with their answers, and its `etag`. `calendarUuid` and `eventUuid` come from `listCalendarEvents` (the `calendarUuid` and `uuid` of an item). For one occurrence of a recurring event pass the `recurrenceId` of the item; without it the whole series is returned and `recurrenceId` is null. A `recurrenceId` that matches no occurrence returns `404`.
Call it before `updateCalendarEvent`, which replaces every field, so the values that should stay can be sent back. `replyable` true means the mailbox was invited by someone else and can answer with `replyToCalendarEvent`. `editable` true means the event can be changed or moved.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_calendar_events_resource import V1CalendarEventsResource
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.CalendarEventsApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    calendar_uuid = '42c370e3-48ae-4286-90c5-d952f28c67cc' # str | Calendar identifier: the `uuid` of a calendar returned by `listCalendars`, or the `calendarUuid` of an event returned by `listCalendarEvents`.
    event_uuid = 'a1b2c3d4-e5f6-7890-abcd-ef1234567890' # str | Event identifier: the `uuid` of an event returned by `listCalendarEvents`. Every occurrence of a recurring event has the same uuid; `recurrenceId` picks one occurrence.
    recurrence_id = '2026-10-05T07:00:00.000000Z' # datetime | `recurrenceId` of one occurrence, copied unchanged from a `listCalendarEvents` item. Omit it for a one-off event or for the whole series. (optional)

    try:
        # Get calendar event
        api_response = api_instance.get_calendar_event(mailbox_resource_id, calendar_uuid, event_uuid, recurrence_id=recurrence_id)
        print("The response of CalendarEventsApi->get_calendar_event:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling CalendarEventsApi->get_calendar_event: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **calendar_uuid** | **str**| Calendar identifier: the &#x60;uuid&#x60; of a calendar returned by &#x60;listCalendars&#x60;, or the &#x60;calendarUuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. | 
 **event_uuid** | **str**| Event identifier: the &#x60;uuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. Every occurrence of a recurring event has the same uuid; &#x60;recurrenceId&#x60; picks one occurrence. | 
 **recurrence_id** | **datetime**| &#x60;recurrenceId&#x60; of one occurrence, copied unchanged from a &#x60;listCalendarEvents&#x60; item. Omit it for a one-off event or for the whole series. | [optional] 

### Return type

[**V1CalendarEventsResource**](V1CalendarEventsResource.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Event payload. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**404** | Resource not found. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **list_calendar_events**
> V1CalendarEventsCollection list_calendar_events(mailbox_resource_id, calendar_uuid, start, end, time_zone=time_zone)

List calendar events

List the events of one calendar that overlap a time range. It covers one calendar only: get the calendars from `listCalendars` and call it for each. The range runs from `start` (inclusive) to `end` (exclusive), at most 32 days; for a longer period call it again with the next range. Recurring events are expanded: each occurrence is a separate item with the same `uuid` and its own `recurrenceId`. Results are not paginated.
Items hold summary fields only. For description, location, attendees and organizer call `getCalendarEvent` with the `calendarUuid`, `uuid` (as `eventUuid`) and `recurrenceId` of the item. Times are in UTC; `timeZone` is the zone the event was created in. `participationStatus` is the answer of the mailbox to an invitation from someone else, null for its own events. `status` CANCELLED means the organizer cancelled the event.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_calendar_events_collection import V1CalendarEventsCollection
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.CalendarEventsApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    calendar_uuid = '42c370e3-48ae-4286-90c5-d952f28c67cc' # str | Calendar identifier: the `uuid` of a calendar returned by `listCalendars`, or the `calendarUuid` of an event returned by `listCalendarEvents`.
    start = '2026-09-28T00:00:00+03:00' # datetime | Start of the range, inclusive. ISO 8601 date-time with offset.
    end = '2026-10-05T00:00:00+03:00' # datetime | End of the range, exclusive. ISO 8601 date-time after `start` and at most 32 days after it.
    time_zone = 'Europe/Vilnius' # str | IANA time zone used to place all-day events and events without a time zone on days, also across a daylight saving change. Defaults to the fixed offset of `start`. (optional)

    try:
        # List calendar events
        api_response = api_instance.list_calendar_events(mailbox_resource_id, calendar_uuid, start, end, time_zone=time_zone)
        print("The response of CalendarEventsApi->list_calendar_events:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling CalendarEventsApi->list_calendar_events: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **calendar_uuid** | **str**| Calendar identifier: the &#x60;uuid&#x60; of a calendar returned by &#x60;listCalendars&#x60;, or the &#x60;calendarUuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. | 
 **start** | **datetime**| Start of the range, inclusive. ISO 8601 date-time with offset. | 
 **end** | **datetime**| End of the range, exclusive. ISO 8601 date-time after &#x60;start&#x60; and at most 32 days after it. | 
 **time_zone** | **str**| IANA time zone used to place all-day events and events without a time zone on days, also across a daylight saving change. Defaults to the fixed offset of &#x60;start&#x60;. | [optional] 

### Return type

[**V1CalendarEventsCollection**](V1CalendarEventsCollection.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Events overlapping the range. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**404** | Resource not found. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **reply_to_calendar_event**
> V1CalendarEventsResource reply_to_calendar_event(mailbox_resource_id, calendar_uuid, event_uuid, v1_calendar_events_reply_request, if_match=if_match)

Reply to calendar event

Answer an invitation from someone else: accept, decline or tentatively accept. It saves the answer on the event and emails it to the organizer, which cannot be recalled. `calendarUuid` and `eventUuid` come from `listCalendarEvents`.
It works only when `getCalendarEvent` returns `replyable` true. An event the mailbox organizes or is not invited to is rejected with `403` and code `ERR_EVENT_NOT_REPLYABLE`, an event the organizer cancelled with `409` and code `ERR_EVENT_CANCELLED`. Send the `recurrenceId` of an item to answer one occurrence of a recurring event, or omit it to answer the whole series. Returns the event with the new `participationStatus`.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_calendar_events_reply_request import V1CalendarEventsReplyRequest
from hostinger_mail_api.models.v1_calendar_events_resource import V1CalendarEventsResource
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.CalendarEventsApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    calendar_uuid = '42c370e3-48ae-4286-90c5-d952f28c67cc' # str | Calendar identifier: the `uuid` of a calendar returned by `listCalendars`, or the `calendarUuid` of an event returned by `listCalendarEvents`.
    event_uuid = 'a1b2c3d4-e5f6-7890-abcd-ef1234567890' # str | Event identifier: the `uuid` of an event returned by `listCalendarEvents`. Every occurrence of a recurring event has the same uuid; `recurrenceId` picks one occurrence.
    v1_calendar_events_reply_request = hostinger_mail_api.V1CalendarEventsReplyRequest() # V1CalendarEventsReplyRequest | 
    if_match = '3c9f1a2b8e04' # str | Optional `etag` from `getCalendarEvent`. When the event changed since that call, the answer is not saved and the request fails with `412`: fetch the event again and retry. Omit it to apply the request to the current version. (optional)

    try:
        # Reply to calendar event
        api_response = api_instance.reply_to_calendar_event(mailbox_resource_id, calendar_uuid, event_uuid, v1_calendar_events_reply_request, if_match=if_match)
        print("The response of CalendarEventsApi->reply_to_calendar_event:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling CalendarEventsApi->reply_to_calendar_event: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **calendar_uuid** | **str**| Calendar identifier: the &#x60;uuid&#x60; of a calendar returned by &#x60;listCalendars&#x60;, or the &#x60;calendarUuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. | 
 **event_uuid** | **str**| Event identifier: the &#x60;uuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. Every occurrence of a recurring event has the same uuid; &#x60;recurrenceId&#x60; picks one occurrence. | 
 **v1_calendar_events_reply_request** | [**V1CalendarEventsReplyRequest**](V1CalendarEventsReplyRequest.md)|  | 
 **if_match** | **str**| Optional &#x60;etag&#x60; from &#x60;getCalendarEvent&#x60;. When the event changed since that call, the answer is not saved and the request fails with &#x60;412&#x60;: fetch the event again and retry. Omit it to apply the request to the current version. | [optional] 

### Return type

[**V1CalendarEventsResource**](V1CalendarEventsResource.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Event with the saved answer. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**404** | Resource not found. |  -  |
**409** | Conflict with the target resource. |  -  |
**412** | The resource changed since the etag sent in &#x60;If-Match&#x60; was read. Nothing was changed: fetch the resource again and retry. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **reschedule_calendar_event**
> V1CalendarEventsResource reschedule_calendar_event(mailbox_resource_id, calendar_uuid, event_uuid, v1_calendar_events_reschedule_request, if_match=if_match)

Reschedule calendar event

Move an event to another time or change its length, keeping everything else (title, attendees, description and so on) as stored, so the event does not have to be fetched first. To change other fields use `updateCalendarEvent`. `calendarUuid` and `eventUuid` come from `listCalendarEvents`. Only an event with `editable` true can be moved; any other is rejected with `403` and code `ERR_EVENT_NOT_EDITABLE`.
For a recurring event, `scope` `this` moves only the occurrence at `recurrenceId`, `future` ends the series before that occurrence and starts a new one with a new `uuid`, `all` (the default) moves the whole series: only the time of day and the length apply and the series keeps the date of its first occurrence.
Attendees receive an email update unless `notifyAttendees` is false. Returns the moved event, or the moved occurrence for `scope` `this`.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_calendar_events_reschedule_request import V1CalendarEventsRescheduleRequest
from hostinger_mail_api.models.v1_calendar_events_resource import V1CalendarEventsResource
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.CalendarEventsApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    calendar_uuid = '42c370e3-48ae-4286-90c5-d952f28c67cc' # str | Calendar identifier: the `uuid` of a calendar returned by `listCalendars`, or the `calendarUuid` of an event returned by `listCalendarEvents`.
    event_uuid = 'a1b2c3d4-e5f6-7890-abcd-ef1234567890' # str | Event identifier: the `uuid` of an event returned by `listCalendarEvents`. Every occurrence of a recurring event has the same uuid; `recurrenceId` picks one occurrence.
    v1_calendar_events_reschedule_request = hostinger_mail_api.V1CalendarEventsRescheduleRequest() # V1CalendarEventsRescheduleRequest | 
    if_match = '3c9f1a2b8e04' # str | Optional `etag` from `getCalendarEvent`. When the event changed since that call, nothing is changed and the request fails with `412`: fetch the event again and retry. Omit it to apply the request to the current version. (optional)

    try:
        # Reschedule calendar event
        api_response = api_instance.reschedule_calendar_event(mailbox_resource_id, calendar_uuid, event_uuid, v1_calendar_events_reschedule_request, if_match=if_match)
        print("The response of CalendarEventsApi->reschedule_calendar_event:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling CalendarEventsApi->reschedule_calendar_event: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **calendar_uuid** | **str**| Calendar identifier: the &#x60;uuid&#x60; of a calendar returned by &#x60;listCalendars&#x60;, or the &#x60;calendarUuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. | 
 **event_uuid** | **str**| Event identifier: the &#x60;uuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. Every occurrence of a recurring event has the same uuid; &#x60;recurrenceId&#x60; picks one occurrence. | 
 **v1_calendar_events_reschedule_request** | [**V1CalendarEventsRescheduleRequest**](V1CalendarEventsRescheduleRequest.md)|  | 
 **if_match** | **str**| Optional &#x60;etag&#x60; from &#x60;getCalendarEvent&#x60;. When the event changed since that call, nothing is changed and the request fails with &#x60;412&#x60;: fetch the event again and retry. Omit it to apply the request to the current version. | [optional] 

### Return type

[**V1CalendarEventsResource**](V1CalendarEventsResource.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Rescheduled event. |  -  |
**400** | The change would leave the event with more unique attendees across all of its occurrences than allowed. &#x60;params.maxAttendees&#x60; holds the limit. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**404** | Resource not found. |  -  |
**412** | The resource changed since the etag sent in &#x60;If-Match&#x60; was read. Nothing was changed: fetch the resource again and retry. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_calendar_event**
> V1CalendarEventsResource update_calendar_event(mailbox_resource_id, calendar_uuid, event_uuid, v1_calendar_events_update_request, if_match=if_match)

Update calendar event

Change the details of an event: title, times, description, location, attendees, recurrence and so on. Every field replaces the stored value and an omitted optional field is cleared, so call `getCalendarEvent` first and send back the values that should stay. To only move an event in time, use `rescheduleCalendarEvent`. Only an event with `editable` true can be changed; any other is rejected with `403` and code `ERR_EVENT_NOT_EDITABLE`.
For a recurring event, `scope` `this` changes only the occurrence at `recurrenceId`, `future` ends the series before that occurrence and starts a new one with a new `uuid`, `all` (the default) changes the whole series, keeping the date of its first occurrence.
Attendees receive an email update, added attendees an invitation and removed ones a cancellation, unless `notifyAttendees` is false. Returns the changed event, or the changed occurrence for `scope` `this`.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_calendar_events_resource import V1CalendarEventsResource
from hostinger_mail_api.models.v1_calendar_events_update_request import V1CalendarEventsUpdateRequest
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.CalendarEventsApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    calendar_uuid = '42c370e3-48ae-4286-90c5-d952f28c67cc' # str | Calendar identifier: the `uuid` of a calendar returned by `listCalendars`, or the `calendarUuid` of an event returned by `listCalendarEvents`.
    event_uuid = 'a1b2c3d4-e5f6-7890-abcd-ef1234567890' # str | Event identifier: the `uuid` of an event returned by `listCalendarEvents`. Every occurrence of a recurring event has the same uuid; `recurrenceId` picks one occurrence.
    v1_calendar_events_update_request = hostinger_mail_api.V1CalendarEventsUpdateRequest() # V1CalendarEventsUpdateRequest | 
    if_match = '3c9f1a2b8e04' # str | Optional `etag` from `getCalendarEvent`. When the event changed since that call, nothing is changed and the request fails with `412`: fetch the event again and retry. Omit it to apply the request to the current version. (optional)

    try:
        # Update calendar event
        api_response = api_instance.update_calendar_event(mailbox_resource_id, calendar_uuid, event_uuid, v1_calendar_events_update_request, if_match=if_match)
        print("The response of CalendarEventsApi->update_calendar_event:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling CalendarEventsApi->update_calendar_event: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **calendar_uuid** | **str**| Calendar identifier: the &#x60;uuid&#x60; of a calendar returned by &#x60;listCalendars&#x60;, or the &#x60;calendarUuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. | 
 **event_uuid** | **str**| Event identifier: the &#x60;uuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. Every occurrence of a recurring event has the same uuid; &#x60;recurrenceId&#x60; picks one occurrence. | 
 **v1_calendar_events_update_request** | [**V1CalendarEventsUpdateRequest**](V1CalendarEventsUpdateRequest.md)|  | 
 **if_match** | **str**| Optional &#x60;etag&#x60; from &#x60;getCalendarEvent&#x60;. When the event changed since that call, nothing is changed and the request fails with &#x60;412&#x60;: fetch the event again and retry. Omit it to apply the request to the current version. | [optional] 

### Return type

[**V1CalendarEventsResource**](V1CalendarEventsResource.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Updated event. |  -  |
**400** | The change would leave the event with more unique attendees across all of its occurrences than allowed. &#x60;params.maxAttendees&#x60; holds the limit. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**404** | Resource not found. |  -  |
**412** | The resource changed since the etag sent in &#x60;If-Match&#x60; was read. Nothing was changed: fetch the resource again and retry. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

