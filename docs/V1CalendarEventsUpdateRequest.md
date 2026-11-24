# V1CalendarEventsUpdateRequest

Body for updating a calendar event. Every field replaces the stored value and an omitted optional field is cleared.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**title** | **str** | Title of the event. | 
**start** | **str** | ISO 8601 date-time with offset; without an offset it is read as UTC. For an all-day event a date is enough (2026-09-28). | 
**end** | **str** | Exclusive end, same format as &#x60;start&#x60;. Required for a timed event and not before &#x60;start&#x60;. For an all-day event the day after the last day (2026-09-29 for one day on 2026-09-28); omitted means one day. | [optional] 
**all_day** | **bool** | &#x60;true&#x60; for an all-day event (dates only, &#x60;timeZone&#x60; ignored), &#x60;false&#x60; for an event at a time of day. | 
**time_zone** | **str** | IANA time zone of the event. Required when &#x60;allDay&#x60; is false, ignored when &#x60;allDay&#x60; is true. | [optional] 
**description** | **str** | Notes of the event. Omitted or null clears it. | [optional] 
**location** | **str** | Place of the event. Omitted or null clears it. | [optional] 
**meeting_link** | **str** | http or https URL of the online meeting. Omitted or null clears it. | [optional] 
**color** | **str** | Color of the event as #RRGGBB or #RRGGBBAA. Omitted or null uses the calendar color. | [optional] 
**recurrence_rule** | [**V1CalendarEventsRecurrenceRule**](V1CalendarEventsRecurrenceRule.md) | Omitted or null makes it a one-off event. A repeating event sends every field of the rule, null when unused: &#x60;frequency&#x60; DAILY, WEEKLY, MONTHLY or YEARLY, &#x60;interval&#x60; 1 to 1000, and &#x60;count&#x60; or &#x60;until&#x60; to end it, not both. | [optional] 
**reminder** | [**V1CalendarEventsReminder**](V1CalendarEventsReminder.md) | Alarm before the start: &#x60;value&#x60; 0 to 1000 and &#x60;unit&#x60;. Omitted or null clears it. | [optional] 
**attendees** | [**List[V1CalendarEventsAttendeeInput]**](V1CalendarEventsAttendeeInput.md) | Full list of invited people. Added addresses receive an invitation and removed ones a cancellation. Unique addresses, at most 100 not counting the mailbox itself, across all occurrences. The own address of the mailbox is stored as accepted and not invited. Omitted, null or empty for none. | [optional] 
**scope** | **str** | For a recurring event: &#x60;this&#x60; changes the occurrence at &#x60;recurrenceId&#x60;, &#x60;future&#x60; changes it and every later one, &#x60;all&#x60; changes the whole series. Omitted or null means &#x60;all&#x60;. Required when &#x60;recurrenceId&#x60; is sent. | [optional] 
**recurrence_id** | **datetime** | &#x60;recurrenceId&#x60; of one occurrence, copied unchanged from a &#x60;listCalendarEvents&#x60; item. Required when &#x60;scope&#x60; is &#x60;this&#x60; or &#x60;future&#x60;, ignored for &#x60;all&#x60;. | [optional] 
**notify_attendees** | **bool** | &#x60;false&#x60; saves the change without emailing attendees, and copies of the event in the calendars of other Hostinger mailboxes are not updated. Omitted or null means &#x60;true&#x60;. | [optional] 

## Example

```python
from hostinger_mail_api.models.v1_calendar_events_update_request import V1CalendarEventsUpdateRequest

# TODO update the JSON string below
json = "{}"
# create an instance of V1CalendarEventsUpdateRequest from a JSON string
v1_calendar_events_update_request_instance = V1CalendarEventsUpdateRequest.from_json(json)
# print the JSON string representation of the object
print(V1CalendarEventsUpdateRequest.to_json())

# convert the object into a dict
v1_calendar_events_update_request_dict = v1_calendar_events_update_request_instance.to_dict()
# create an instance of V1CalendarEventsUpdateRequest from a dict
v1_calendar_events_update_request_from_dict = V1CalendarEventsUpdateRequest.from_dict(v1_calendar_events_update_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


