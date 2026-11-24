# V1CalendarEventsRecurrenceRule

How an event repeats. Every field is always present, null when unused.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**frequency** | **str** | Unit of repetition. Only DAILY, WEEKLY, MONTHLY and YEARLY can be written; SECONDLY, MINUTELY and HOURLY appear only on events created by other calendar applications. | 
**interval** | **int** | Repeat every this many units of &#x60;frequency&#x60;. 1 to 1000 when writing. | 
**by_day** | [**List[V1CalendarEventsRecurrenceDay]**](V1CalendarEventsRecurrenceDay.md) | Weekdays the event repeats on. Null when unused. | 
**by_month_day** | **List[int]** | Days of the month, 1 to 31. Negative values count from the end of the month: -1 is the last day. Always null for a WEEKLY rule. | 
**by_month** | **List[int]** | Months, 1 is January. Null when unused. | 
**count** | **int** | Number of occurrences after which the series ends, at most 1000 when writing. Never set together with &#x60;until&#x60;. | 
**until** | **datetime** | Moment after which the series ends, not before the start of the event. Never set together with &#x60;count&#x60;. | 
**week_start** | **str** | First day of the week used by the rule. Null when not set. | 

## Example

```python
from hostinger_mail_api.models.v1_calendar_events_recurrence_rule import V1CalendarEventsRecurrenceRule

# TODO update the JSON string below
json = "{}"
# create an instance of V1CalendarEventsRecurrenceRule from a JSON string
v1_calendar_events_recurrence_rule_instance = V1CalendarEventsRecurrenceRule.from_json(json)
# print the JSON string representation of the object
print(V1CalendarEventsRecurrenceRule.to_json())

# convert the object into a dict
v1_calendar_events_recurrence_rule_dict = v1_calendar_events_recurrence_rule_instance.to_dict()
# create an instance of V1CalendarEventsRecurrenceRule from a dict
v1_calendar_events_recurrence_rule_from_dict = V1CalendarEventsRecurrenceRule.from_dict(v1_calendar_events_recurrence_rule_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


