# V1CalendarEventsAttendeeInput

Person to invite to an event.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **str** | Display name of the attendee, null when unknown. | [optional] 
**email** | **str** | Email address of the attendee. | 

## Example

```python
from hostinger_mail_api.models.v1_calendar_events_attendee_input import V1CalendarEventsAttendeeInput

# TODO update the JSON string below
json = "{}"
# create an instance of V1CalendarEventsAttendeeInput from a JSON string
v1_calendar_events_attendee_input_instance = V1CalendarEventsAttendeeInput.from_json(json)
# print the JSON string representation of the object
print(V1CalendarEventsAttendeeInput.to_json())

# convert the object into a dict
v1_calendar_events_attendee_input_dict = v1_calendar_events_attendee_input_instance.to_dict()
# create an instance of V1CalendarEventsAttendeeInput from a dict
v1_calendar_events_attendee_input_from_dict = V1CalendarEventsAttendeeInput.from_dict(v1_calendar_events_attendee_input_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


