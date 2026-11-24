# V1CalendarEventsReminder

Alarm of an event: how long before the start it fires.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**value** | **int** | How many units before the start. 0 is at the start time. At most 1000 when writing. | 
**unit** | **str** |  | 

## Example

```python
from hostinger_mail_api.models.v1_calendar_events_reminder import V1CalendarEventsReminder

# TODO update the JSON string below
json = "{}"
# create an instance of V1CalendarEventsReminder from a JSON string
v1_calendar_events_reminder_instance = V1CalendarEventsReminder.from_json(json)
# print the JSON string representation of the object
print(V1CalendarEventsReminder.to_json())

# convert the object into a dict
v1_calendar_events_reminder_dict = v1_calendar_events_reminder_instance.to_dict()
# create an instance of V1CalendarEventsReminder from a dict
v1_calendar_events_reminder_from_dict = V1CalendarEventsReminder.from_dict(v1_calendar_events_reminder_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


