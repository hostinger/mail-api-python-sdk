# V1FeedbackSubmitRequest

Feedback the user wants to send to the Hostinger mail team. The message is scrubbed of tokens, JWTs and key/secret/password values before validation and storage, so the length limit applies to the scrubbed text.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**score** | **int** | The user&#39;s rating of the Hostinger Email API: 1 (poor) to 10 (excellent). | 
**message** | **str** | The user&#39;s feedback in their own words. Never include tokens, passwords or email contents. | 

## Example

```python
from hostinger_mail_api.models.v1_feedback_submit_request import V1FeedbackSubmitRequest

# TODO update the JSON string below
json = "{}"
# create an instance of V1FeedbackSubmitRequest from a JSON string
v1_feedback_submit_request_instance = V1FeedbackSubmitRequest.from_json(json)
# print the JSON string representation of the object
print(V1FeedbackSubmitRequest.to_json())

# convert the object into a dict
v1_feedback_submit_request_dict = v1_feedback_submit_request_instance.to_dict()
# create an instance of V1FeedbackSubmitRequest from a dict
v1_feedback_submit_request_from_dict = V1FeedbackSubmitRequest.from_dict(v1_feedback_submit_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


