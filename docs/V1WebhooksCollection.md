# V1WebhooksCollection

Paginated list of webhooks.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**List[V1WebhooksWebhook]**](V1WebhooksWebhook.md) |  | 
**pagination** | [**Pagination**](Pagination.md) |  | 

## Example

```python
from hostinger_mail_api.models.v1_webhooks_collection import V1WebhooksCollection

# TODO update the JSON string below
json = "{}"
# create an instance of V1WebhooksCollection from a JSON string
v1_webhooks_collection_instance = V1WebhooksCollection.from_json(json)
# print the JSON string representation of the object
print(V1WebhooksCollection.to_json())

# convert the object into a dict
v1_webhooks_collection_dict = v1_webhooks_collection_instance.to_dict()
# create an instance of V1WebhooksCollection from a dict
v1_webhooks_collection_from_dict = V1WebhooksCollection.from_dict(v1_webhooks_collection_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


