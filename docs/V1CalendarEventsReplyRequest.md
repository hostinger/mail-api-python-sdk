# V1CalendarEventsReplyRequest

Body for answering an invitation.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**participation_status** | **str** | The answer to the invitation. | 
**recurrence_id** | **datetime** | &#x60;recurrenceId&#x60; of one occurrence, copied unchanged from a &#x60;listCalendarEvents&#x60; item, to answer only that occurrence. Omitted or null answers the whole event. | [optional] 

## Example

```python
from hostinger_mail_api.models.v1_calendar_events_reply_request import V1CalendarEventsReplyRequest

# TODO update the JSON string below
json = "{}"
# create an instance of V1CalendarEventsReplyRequest from a JSON string
v1_calendar_events_reply_request_instance = V1CalendarEventsReplyRequest.from_json(json)
# print the JSON string representation of the object
print(V1CalendarEventsReplyRequest.to_json())

# convert the object into a dict
v1_calendar_events_reply_request_dict = v1_calendar_events_reply_request_instance.to_dict()
# create an instance of V1CalendarEventsReplyRequest from a dict
v1_calendar_events_reply_request_from_dict = V1CalendarEventsReplyRequest.from_dict(v1_calendar_events_reply_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


