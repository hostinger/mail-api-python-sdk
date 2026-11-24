# V1CalendarsCollection

Paginated list of calendars.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**List[V1CalendarsCalendar]**](V1CalendarsCalendar.md) |  | 
**pagination** | [**Pagination**](Pagination.md) |  | 

## Example

```python
from hostinger_mail_api.models.v1_calendars_collection import V1CalendarsCollection

# TODO update the JSON string below
json = "{}"
# create an instance of V1CalendarsCollection from a JSON string
v1_calendars_collection_instance = V1CalendarsCollection.from_json(json)
# print the JSON string representation of the object
print(V1CalendarsCollection.to_json())

# convert the object into a dict
v1_calendars_collection_dict = v1_calendars_collection_instance.to_dict()
# create an instance of V1CalendarsCollection from a dict
v1_calendars_collection_from_dict = V1CalendarsCollection.from_dict(v1_calendars_collection_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


