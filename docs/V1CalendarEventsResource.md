# V1CalendarEventsResource

Single calendar event payload.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**V1CalendarEventsEvent**](V1CalendarEventsEvent.md) |  | 

## Example

```python
from hostinger_mail_api.models.v1_calendar_events_resource import V1CalendarEventsResource

# TODO update the JSON string below
json = "{}"
# create an instance of V1CalendarEventsResource from a JSON string
v1_calendar_events_resource_instance = V1CalendarEventsResource.from_json(json)
# print the JSON string representation of the object
print(V1CalendarEventsResource.to_json())

# convert the object into a dict
v1_calendar_events_resource_dict = v1_calendar_events_resource_instance.to_dict()
# create an instance of V1CalendarEventsResource from a dict
v1_calendar_events_resource_from_dict = V1CalendarEventsResource.from_dict(v1_calendar_events_resource_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


