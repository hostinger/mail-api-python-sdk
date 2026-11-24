# V1CalendarsCreateRequest

Body for creating a calendar.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**display_name** | **str** | Name of the calendar. | 
**description** | **str** | Optional free-text note about the calendar. | [optional] 
**color** | **str** | Hex color as #RRGGBB or #RRGGBBAA. Omitted or null uses the default color. | [optional] 
**visible** | **bool** | Whether the mailbox shows the calendar in its calendar view. Omitted or null means true. | [optional] 

## Example

```python
from hostinger_mail_api.models.v1_calendars_create_request import V1CalendarsCreateRequest

# TODO update the JSON string below
json = "{}"
# create an instance of V1CalendarsCreateRequest from a JSON string
v1_calendars_create_request_instance = V1CalendarsCreateRequest.from_json(json)
# print the JSON string representation of the object
print(V1CalendarsCreateRequest.to_json())

# convert the object into a dict
v1_calendars_create_request_dict = v1_calendars_create_request_instance.to_dict()
# create an instance of V1CalendarsCreateRequest from a dict
v1_calendars_create_request_from_dict = V1CalendarsCreateRequest.from_dict(v1_calendars_create_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


