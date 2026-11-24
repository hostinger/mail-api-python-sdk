# V1CalendarEventsRecurrenceDay

One weekday of a recurrence rule.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**day** | **str** |  | 
**position** | **int** | Which such weekday in the month or year, for a MONTHLY or YEARLY rule only: 1 is the first, -1 the last, never 0. Null means every such weekday and is the only value allowed for other frequencies. | 

## Example

```python
from hostinger_mail_api.models.v1_calendar_events_recurrence_day import V1CalendarEventsRecurrenceDay

# TODO update the JSON string below
json = "{}"
# create an instance of V1CalendarEventsRecurrenceDay from a JSON string
v1_calendar_events_recurrence_day_instance = V1CalendarEventsRecurrenceDay.from_json(json)
# print the JSON string representation of the object
print(V1CalendarEventsRecurrenceDay.to_json())

# convert the object into a dict
v1_calendar_events_recurrence_day_dict = v1_calendar_events_recurrence_day_instance.to_dict()
# create an instance of V1CalendarEventsRecurrenceDay from a dict
v1_calendar_events_recurrence_day_from_dict = V1CalendarEventsRecurrenceDay.from_dict(v1_calendar_events_recurrence_day_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


