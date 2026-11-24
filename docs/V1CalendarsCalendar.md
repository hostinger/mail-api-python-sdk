# V1CalendarsCalendar

Calendar of a managed mailbox: one it owns or one shared with it.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uuid** | **str** | Calendar identifier, the &#x60;calendarUuid&#x60; of the calendar and calendar event endpoints. | 
**display_name** | **str** |  | 
**description** | **str** |  | 
**color** | **str** | Hex color as #RRGGBB or #RRGGBBAA. | 
**default** | **bool** | Whether this is the default calendar of the mailbox. New events go here unless another calendar is named. | 
**visible** | **bool** | Whether the mailbox shows the calendar in its calendar view. A preference of this mailbox, not shared with other users of the calendar. Events of a hidden calendar still exist. | 

## Example

```python
from hostinger_mail_api.models.v1_calendars_calendar import V1CalendarsCalendar

# TODO update the JSON string below
json = "{}"
# create an instance of V1CalendarsCalendar from a JSON string
v1_calendars_calendar_instance = V1CalendarsCalendar.from_json(json)
# print the JSON string representation of the object
print(V1CalendarsCalendar.to_json())

# convert the object into a dict
v1_calendars_calendar_dict = v1_calendars_calendar_instance.to_dict()
# create an instance of V1CalendarsCalendar from a dict
v1_calendars_calendar_from_dict = V1CalendarsCalendar.from_dict(v1_calendars_calendar_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


