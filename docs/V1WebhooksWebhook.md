# V1WebhooksWebhook

Webhook configured for a managed mailbox.

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

## Example

```python
from hostinger_mail_api.models.v1_webhooks_webhook import V1WebhooksWebhook

# TODO update the JSON string below
json = "{}"
# create an instance of V1WebhooksWebhook from a JSON string
v1_webhooks_webhook_instance = V1WebhooksWebhook.from_json(json)
# print the JSON string representation of the object
print(V1WebhooksWebhook.to_json())

# convert the object into a dict
v1_webhooks_webhook_dict = v1_webhooks_webhook_instance.to_dict()
# create an instance of V1WebhooksWebhook from a dict
v1_webhooks_webhook_from_dict = V1WebhooksWebhook.from_dict(v1_webhooks_webhook_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


