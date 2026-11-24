# V1CalendarEventsAttendee

Attendee of an event with their answer to the invitation.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **str** |  | 
**email** | **str** |  | 
**participation_status** | **str** | Answer of the attendee. NEEDS-ACTION means no answer yet. | 

## Example

```python
from hostinger_mail_api.models.v1_calendar_events_attendee import V1CalendarEventsAttendee

# TODO update the JSON string below
json = "{}"
# create an instance of V1CalendarEventsAttendee from a JSON string
v1_calendar_events_attendee_instance = V1CalendarEventsAttendee.from_json(json)
# print the JSON string representation of the object
print(V1CalendarEventsAttendee.to_json())

# convert the object into a dict
v1_calendar_events_attendee_dict = v1_calendar_events_attendee_instance.to_dict()
# create an instance of V1CalendarEventsAttendee from a dict
v1_calendar_events_attendee_from_dict = V1CalendarEventsAttendee.from_dict(v1_calendar_events_attendee_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


