# V1CalendarEventsCollectionMeta


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**truncated** | **bool** | Whether some events were left out because the calendar holds too many to list in one request. | 

## Example

```python
from hostinger_mail_api.models.v1_calendar_events_collection_meta import V1CalendarEventsCollectionMeta

# TODO update the JSON string below
json = "{}"
# create an instance of V1CalendarEventsCollectionMeta from a JSON string
v1_calendar_events_collection_meta_instance = V1CalendarEventsCollectionMeta.from_json(json)
# print the JSON string representation of the object
print(V1CalendarEventsCollectionMeta.to_json())

# convert the object into a dict
v1_calendar_events_collection_meta_dict = v1_calendar_events_collection_meta_instance.to_dict()
# create an instance of V1CalendarEventsCollectionMeta from a dict
v1_calendar_events_collection_meta_from_dict = V1CalendarEventsCollectionMeta.from_dict(v1_calendar_events_collection_meta_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


