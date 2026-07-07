# V1WebhooksUpdateRequest

Body for partially updating a webhook. All fields optional; only present fields are applied.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **str** |  | [optional] 
**description** | **str** |  | [optional] 
**events** | **List[str]** |  | [optional] 
**status** | **str** |  | [optional] 
**url** | **str** |  | [optional] 

## Example

```python
from hostinger_email_api.models.v1_webhooks_update_request import V1WebhooksUpdateRequest

# TODO update the JSON string below
json = "{}"
# create an instance of V1WebhooksUpdateRequest from a JSON string
v1_webhooks_update_request_instance = V1WebhooksUpdateRequest.from_json(json)
# print the JSON string representation of the object
print(V1WebhooksUpdateRequest.to_json())

# convert the object into a dict
v1_webhooks_update_request_dict = v1_webhooks_update_request_instance.to_dict()
# create an instance of V1WebhooksUpdateRequest from a dict
v1_webhooks_update_request_from_dict = V1WebhooksUpdateRequest.from_dict(v1_webhooks_update_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


