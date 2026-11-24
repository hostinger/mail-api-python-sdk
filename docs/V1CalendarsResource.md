# V1CalendarsResource

Single calendar payload.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**V1CalendarsCalendar**](V1CalendarsCalendar.md) |  | 

## Example

```python
from hostinger_mail_api.models.v1_calendars_resource import V1CalendarsResource

# TODO update the JSON string below
json = "{}"
# create an instance of V1CalendarsResource from a JSON string
v1_calendars_resource_instance = V1CalendarsResource.from_json(json)
# print the JSON string representation of the object
print(V1CalendarsResource.to_json())

# convert the object into a dict
v1_calendars_resource_dict = v1_calendars_resource_instance.to_dict()
# create an instance of V1CalendarsResource from a dict
v1_calendars_resource_from_dict = V1CalendarsResource.from_dict(v1_calendars_resource_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


