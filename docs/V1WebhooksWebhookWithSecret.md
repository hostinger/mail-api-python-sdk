# V1WebhooksWebhookWithSecret

Webhook payload that includes the one-time `secret`. Returned at creation and after secret regeneration. The secret is delivered as a bearer token on every webhook request (`Authorization: Bearer <secret>`); store it securely as it is not returned again.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **str** | Unique webhook identifier (UUID v7). | 
**account_resource_id** | **str** | Resource ID of the mailbox this webhook is attached to. | 
**mailbox** | **str** | Email address of the mailbox. | 
**name** | **str** |  | 
**description** | **str** |  | 
**events** | **List[str]** |  | 
**status** | **str** |  | 
**url** | **str** |  | 
**created_at** | **datetime** |  | 
**updated_at** | **datetime** |  | 
**secret** | **str** |  | 

## Example

```python
from hostinger_email_api.models.v1_webhooks_webhook_with_secret import V1WebhooksWebhookWithSecret

# TODO update the JSON string below
json = "{}"
# create an instance of V1WebhooksWebhookWithSecret from a JSON string
v1_webhooks_webhook_with_secret_instance = V1WebhooksWebhookWithSecret.from_json(json)
# print the JSON string representation of the object
print(V1WebhooksWebhookWithSecret.to_json())

# convert the object into a dict
v1_webhooks_webhook_with_secret_dict = v1_webhooks_webhook_with_secret_instance.to_dict()
# create an instance of V1WebhooksWebhookWithSecret from a dict
v1_webhooks_webhook_with_secret_from_dict = V1WebhooksWebhookWithSecret.from_dict(v1_webhooks_webhook_with_secret_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


