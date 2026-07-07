# V1WebhooksResource

Single webhook payload.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**V1WebhooksWebhook**](V1WebhooksWebhook.md) |  | 

## Example

```python
from hostinger_email_api.models.v1_webhooks_resource import V1WebhooksResource

# TODO update the JSON string below
json = "{}"
# create an instance of V1WebhooksResource from a JSON string
v1_webhooks_resource_instance = V1WebhooksResource.from_json(json)
# print the JSON string representation of the object
print(V1WebhooksResource.to_json())

# convert the object into a dict
v1_webhooks_resource_dict = v1_webhooks_resource_instance.to_dict()
# create an instance of V1WebhooksResource from a dict
v1_webhooks_resource_from_dict = V1WebhooksResource.from_dict(v1_webhooks_resource_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


