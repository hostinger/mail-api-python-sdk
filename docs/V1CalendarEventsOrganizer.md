# V1CalendarEventsOrganizer

Organizer of an event.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **str** |  | 
**email** | **str** |  | 

## Example

```python
from hostinger_mail_api.models.v1_calendar_events_organizer import V1CalendarEventsOrganizer

# TODO update the JSON string below
json = "{}"
# create an instance of V1CalendarEventsOrganizer from a JSON string
v1_calendar_events_organizer_instance = V1CalendarEventsOrganizer.from_json(json)
# print the JSON string representation of the object
print(V1CalendarEventsOrganizer.to_json())

# convert the object into a dict
v1_calendar_events_organizer_dict = v1_calendar_events_organizer_instance.to_dict()
# create an instance of V1CalendarEventsOrganizer from a dict
v1_calendar_events_organizer_from_dict = V1CalendarEventsOrganizer.from_dict(v1_calendar_events_organizer_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


