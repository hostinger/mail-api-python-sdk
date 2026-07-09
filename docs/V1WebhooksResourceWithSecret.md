# V1WebhooksResourceWithSecret

Single webhook payload including the one-time secret.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**V1WebhooksWebhookWithSecret**](V1WebhooksWebhookWithSecret.md) |  | 

## Example

```python
from hostinger_mail_api.models.v1_webhooks_resource_with_secret import V1WebhooksResourceWithSecret

# TODO update the JSON string below
json = "{}"
# create an instance of V1WebhooksResourceWithSecret from a JSON string
v1_webhooks_resource_with_secret_instance = V1WebhooksResourceWithSecret.from_json(json)
# print the JSON string representation of the object
print(V1WebhooksResourceWithSecret.to_json())

# convert the object into a dict
v1_webhooks_resource_with_secret_dict = v1_webhooks_resource_with_secret_instance.to_dict()
# create an instance of V1WebhooksResourceWithSecret from a dict
v1_webhooks_resource_with_secret_from_dict = V1WebhooksResourceWithSecret.from_dict(v1_webhooks_resource_with_secret_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


