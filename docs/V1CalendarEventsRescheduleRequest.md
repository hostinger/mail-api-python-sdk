# V1CalendarEventsRescheduleRequest

Body for moving a calendar event to another time or changing its length.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**start** | **str** | ISO 8601 date-time with offset; without an offset it is read as UTC. For an all-day event a date is enough (2026-09-28). | 
**end** | **str** | Exclusive end, same format as &#x60;start&#x60;. Required for a timed event and not before &#x60;start&#x60;. For an all-day event the day after the last day (2026-09-29 for one day on 2026-09-28); omitted means one day. | [optional] 
**all_day** | **bool** | &#x60;true&#x60; for an all-day event (dates only, &#x60;timeZone&#x60; ignored), &#x60;false&#x60; for an event at a time of day. | 
**time_zone** | **str** | IANA time zone of the event. Required when &#x60;allDay&#x60; is false, ignored when &#x60;allDay&#x60; is true. | [optional] 
**scope** | **str** | For a recurring event: &#x60;this&#x60; moves the occurrence at &#x60;recurrenceId&#x60;, &#x60;future&#x60; moves it and every later one, &#x60;all&#x60; moves the whole series. Omitted or null means &#x60;all&#x60;. Required when &#x60;recurrenceId&#x60; is sent. | [optional] 
**recurrence_id** | **datetime** | &#x60;recurrenceId&#x60; of one occurrence, copied unchanged from a &#x60;listCalendarEvents&#x60; item. Required when &#x60;scope&#x60; is &#x60;this&#x60; or &#x60;future&#x60;, ignored for &#x60;all&#x60;. | [optional] 
**notify_attendees** | **bool** | &#x60;false&#x60; saves the change without emailing attendees, and copies of the event in the calendars of other Hostinger mailboxes are not updated. Omitted or null means &#x60;true&#x60;. | [optional] 

## Example

```python
from hostinger_mail_api.models.v1_calendar_events_reschedule_request import V1CalendarEventsRescheduleRequest

# TODO update the JSON string below
json = "{}"
# create an instance of V1CalendarEventsRescheduleRequest from a JSON string
v1_calendar_events_reschedule_request_instance = V1CalendarEventsRescheduleRequest.from_json(json)
# print the JSON string representation of the object
print(V1CalendarEventsRescheduleRequest.to_json())

# convert the object into a dict
v1_calendar_events_reschedule_request_dict = v1_calendar_events_reschedule_request_instance.to_dict()
# create an instance of V1CalendarEventsRescheduleRequest from a dict
v1_calendar_events_reschedule_request_from_dict = V1CalendarEventsRescheduleRequest.from_dict(v1_calendar_events_reschedule_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


