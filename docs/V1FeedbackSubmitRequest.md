# V1FeedbackSubmitRequest

Feedback about the Mail API or the MCP server. The message is scrubbed of tokens, JWTs and key/secret/password values before validation and storage, so the length limit applies to the scrubbed text.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**score** | **int** | How well the API served the task: 1 (poor) to 10 (excellent). | 
**message** | **str** | What happened and what was expected, including the operation and status code involved. Never include tokens, passwords or email contents. | 

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


