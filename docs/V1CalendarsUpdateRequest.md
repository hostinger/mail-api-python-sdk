# V1CalendarsUpdateRequest

Body for updating a calendar. Name, description and color replace the stored values.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**display_name** | **str** | Name of the calendar. | 
**description** | **str** | Free-text note about the calendar. Omitted or null clears it. | [optional] 
**color** | **str** | Hex color as #RRGGBB or #RRGGBBAA. Omitted or null resets it to the default color. | [optional] 
**visible** | **bool** | Whether the mailbox shows the calendar in its calendar view. Omitted or null keeps the current value. | [optional] 

## Example

```python
from hostinger_mail_api.models.v1_calendars_update_request import V1CalendarsUpdateRequest

# TODO update the JSON string below
json = "{}"
# create an instance of V1CalendarsUpdateRequest from a JSON string
v1_calendars_update_request_instance = V1CalendarsUpdateRequest.from_json(json)
# print the JSON string representation of the object
print(V1CalendarsUpdateRequest.to_json())

# convert the object into a dict
v1_calendars_update_request_dict = v1_calendars_update_request_instance.to_dict()
# create an instance of V1CalendarsUpdateRequest from a dict
v1_calendars_update_request_from_dict = V1CalendarsUpdateRequest.from_dict(v1_calendars_update_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


