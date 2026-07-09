# V1WebhooksCreateRequest

Body for creating a webhook.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **str** |  | 
**description** | **str** |  | [optional] 
**events** | **List[str]** |  | 
**status** | **str** |  | [optional] [default to 'active']
**url** | **str** |  | 

## Example

```python
from hostinger_mail_api.models.v1_webhooks_create_request import V1WebhooksCreateRequest

# TODO update the JSON string below
json = "{}"
# create an instance of V1WebhooksCreateRequest from a JSON string
v1_webhooks_create_request_instance = V1WebhooksCreateRequest.from_json(json)
# print the JSON string representation of the object
print(V1WebhooksCreateRequest.to_json())

# convert the object into a dict
v1_webhooks_create_request_dict = v1_webhooks_create_request_instance.to_dict()
# create an instance of V1WebhooksCreateRequest from a dict
v1_webhooks_create_request_from_dict = V1WebhooksCreateRequest.from_dict(v1_webhooks_create_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


