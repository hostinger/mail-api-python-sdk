# V1CalendarEventsCollection

Calendar events overlapping the requested time range. Not paginated.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**List[V1CalendarEventsEventListItem]**](V1CalendarEventsEventListItem.md) |  | 
**meta** | [**V1CalendarEventsCollectionMeta**](V1CalendarEventsCollectionMeta.md) |  | 

## Example

```python
from hostinger_mail_api.models.v1_calendar_events_collection import V1CalendarEventsCollection

# TODO update the JSON string below
json = "{}"
# create an instance of V1CalendarEventsCollection from a JSON string
v1_calendar_events_collection_instance = V1CalendarEventsCollection.from_json(json)
# print the JSON string representation of the object
print(V1CalendarEventsCollection.to_json())

# convert the object into a dict
v1_calendar_events_collection_dict = v1_calendar_events_collection_instance.to_dict()
# create an instance of V1CalendarEventsCollection from a dict
v1_calendar_events_collection_from_dict = V1CalendarEventsCollection.from_dict(v1_calendar_events_collection_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


