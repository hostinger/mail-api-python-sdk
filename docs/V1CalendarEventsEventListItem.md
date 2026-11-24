# V1CalendarEventsEventListItem

Summary of one calendar event or of one occurrence of a recurring event.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uuid** | **str** | Event identifier, the &#x60;eventUuid&#x60; of the calendar event endpoints. Every occurrence of a recurring event has the same uuid. | 
**calendar_uuid** | **str** | Identifier of the calendar the event is stored in. | 
**recurrence_id** | **datetime** | Identifies one occurrence of a recurring event. Null for a one-off event or for the series itself. | 
**title** | **str** |  | 
**start** | **datetime** | Start in UTC. When &#x60;allDay&#x60; is true, the date at midnight (2026-09-29T00:00:00.000000Z). An event stored without a time zone keeps its wall-clock time (09:00 is 09:00:00.000000Z). | 
**end** | **datetime** | Exclusive end, same form as &#x60;start&#x60;. When &#x60;allDay&#x60; is true, midnight of the day after the last day of the event (2026-09-30T00:00:00.000000Z for a one-day event on 2026-09-29). | 
**all_day** | **bool** |  | 
**time_zone** | **str** | IANA time zone the event is stored in. Null when it has none. | 
**editable** | **bool** | Whether &#x60;updateCalendarEvent&#x60;, &#x60;rescheduleCalendarEvent&#x60; and &#x60;deleteCalendarEvent&#x60; can change the event. | 
**color** | **str** | Color of the event. The calendar color when the event has none or is an invitation from someone else. | 
**participation_status** | **str** | Answer of the mailbox to an invitation from someone else. Null for its own events. | 
**status** | **str** | CANCELLED when the organizer cancelled the event, CONFIRMED otherwise. | 

## Example

```python
from hostinger_mail_api.models.v1_calendar_events_event_list_item import V1CalendarEventsEventListItem

# TODO update the JSON string below
json = "{}"
# create an instance of V1CalendarEventsEventListItem from a JSON string
v1_calendar_events_event_list_item_instance = V1CalendarEventsEventListItem.from_json(json)
# print the JSON string representation of the object
print(V1CalendarEventsEventListItem.to_json())

# convert the object into a dict
v1_calendar_events_event_list_item_dict = v1_calendar_events_event_list_item_instance.to_dict()
# create an instance of V1CalendarEventsEventListItem from a dict
v1_calendar_events_event_list_item_from_dict = V1CalendarEventsEventListItem.from_dict(v1_calendar_events_event_list_item_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


